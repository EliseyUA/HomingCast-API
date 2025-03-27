## Here is the example code

---

More information about [Caster](Caster.md)

More information about [Properties](Properties.md)

---

```luau
local tool = script.Parent
local HomingCast = require(game.ReplicatedStorage.HomingCast)

local Caster = HomingCast.new()

local params = RaycastParams.new()
params.FilterType = Enum.RaycastFilterType.Exclude
params.FilterDescendantsInstances = {tool}

-- Setting the properties

local Properties = HomingCast.NewProperties()
Properties.MaxDistance = 3000
Properties.MaxFlyTime = 10
Properties.CosmeticBulletTemplate = game.ReplicatedStorage.RocketProjectile
Properties.RayCastParams = params
Properties.PredictionEquation = 2
Properties.RotationSpeed = 50
Properties.MaxAngleToLoseTheTarget = 70
Properties.RaysPerMove = 1
Properties.CosmeticBulletFolder = workspace.BulletFolder

local debounce = false

local function customExplosion(position)
	local explosion = Instance.new("Explosion")
	explosion.BlastPressure = 0
	explosion.DestroyJointRadiusPercent = 0
	explosion.BlastRadius = 0
	explosion.Position = position
	explosion.Parent = workspace
end

tool.Equipped:Connect(function()
	debounce = true
end)

tool.Unequipped:Connect(function()
	debounce = false
end)

tool.Activated:Connect(function()
	local ActiveCast = caster:Fire(tool.LookVectorPart.Position, tool.LookVectorPart.CFrame.LookVector, 200, workspace.Target, Properties) -- 30 studs rocket
end)

local function PositionChanged(Cast, Position: Vector3, Direction: Vector3, Distance: number, Target: Vector3 | BasePart, CosmeticBullet: BasePart?, UserData: {})
	if CosmeticBullet then
		local BulletSize = CosmeticBullet.Size.Z / 2
		local Offset = CFrame.new(0, 0, -(Distance - BulletSize))
		CosmeticBullet.CFrame = CFrame.lookAt(Position, Position + Direction):ToWorldSpace(Offset)
	end
end

local function RayHit(Cast, RayCastResult: RaycastResult, Direction: Vector3, Speed, CosmeticBullet: BasePart?, UserData: {})
	customExplosion(RayCastResult.Position)
	if CosmeticBullet then CosmeticBullet:Destroy() end
end

local function Terminated(cast, Reason: string, CosmeticBullet: BasePart?, UserData: {})
	if CosmeticBullet then CosmeticBullet:Destroy() end
end

local function LostTarget(cast, LostTarget: Vector3 | BasePart, Position: Vector3, Direction: Vector3, CosmeticBullet: BasePart?, UserData: {})
	print('Cast lost its target! Target:', LostTarget)
end

caster.PositionChanged:Connect(PositionChanged)
caster.RayHit:Connect(RayHit)
caster.Terminated:Connect(Terminated)
caster.TargetLost:Connect(LostTarget)
```