## At this page, you can see all methods that are currently implemented

!!! info "Remember!"
    These methods must be applied to [InfoCast](InfoCast.md)

---
### TerminateCast
```lua
InfoCast:TerminateCast()
```
Terminates the cast.

---
### SetSpeed
```lua
InfoCast:SetSpeed(Speed: number)
```
Sets the speed of the cast.

---
### AddSpeed
```lua
InfoCast:AddSpeed(Speed: number)
```
Adds the speed to the cast.

---
### GetSpeed
```lua
InfoCast:GetSpeed(): number
```
Returns the current speed of the cast.

---
### GetPosition
```lua
InfoCast:GetPosition(): Vector3
```
Returns the current position of the cast.

---
### GetDirection
```lua
InfoCast:GetDirection(): Vector3
```
Returns the current direction of the cast.

---
### SetDirection
```lua
InfoCast:SetDirection(Direction: Vector3)
```
Sets the direction of the cast.

---
### SetPosition
```lua
InfoCast:SetPosition(Position: Vector3)
```
Sets the position of the cast.

---
!!! info "Remember!"
    Angles must not be in radians.

---
### SetRotationSpeed
```lua
InfoCast:SetRotationSpeed(Number: number)
```
Sets the speed of rotation of the cast.

---
### AddRotationSpeed
```lua
InfoCast:AddRotationSpeed(Number: number)
```
Adds the speed of rotation to the cast.

---
### SetMaxAngle
```lua
InfoCast:SetMaxAngle(Angle: number)
```
Sets the angle at which the cast loses its target.

---
### AddMaxAngle
```lua
InfoCast:AddMaxAngle(Angle: number)
```
Adds to the angle at which the cast loses its target.

---
### Pause
```lua
InfoCast:Pause()
```
Pauses the simulation of the cast.

---
### UnPause
```lua
InfoCast:UnPause()
```
Resumes the simulation of the cast.

---
### IsPaused
```lua
InfoCast:IsPaused(): boolean
```
Returns `true` if the cast is paused, otherwise `false`.

---
### PauseTrajectory
```lua
InfoCast:PauseTrajectory()
```
Pauses the trajectory from advancing.

---
### UnPauseTrajectory
```lua
InfoCast:UnPauseTrajectory()
```
Resumes the trajectory.

---
### IsPausedTrajectory
```lua
InfoCast:IsPausedTrajectory(): boolean
```
Returns `true` if the trajectory is paused, otherwise `false`.

---
### GetProgress
```lua
InfoCast:GetProgress(): (number, number, number?, number?)
```
Returns the current covered distance and total flight time. If the covered distance is greater than or equal to `0`, it also returns the percentage of how far the cast has traveled. The same applies to the total flight time.

---
### UpdateRaycastParams
```lua
InfoCast:UpdateRaycastParams(Params: RaycastParams)
```
Sets new raycast parameters for the cast.

---
### SetXscale
```lua
InfoCast:SetXscale(index: number, value: number)
```
Sets the X scale of a trajectory point to a given value (from `0` to `1`). The `index` determines the position in the trajectory list.

---
### SetYscale
```lua
InfoCast:SetYscale(index: number, value: number)
```
Sets the Y scale of a trajectory point to a given value (from `-1` to `1`). The `index` determines the position in the trajectory list.

---
### GetDistanceToTarget
```lua
InfoCast:GetDistanceToTarget(): number?
```
Returns the distance to the target if the target is not `nil`, otherwise returns `nil`.

---
### GetTargetInfo
```lua
InfoCast:GetTargetInfo(): (Vector3?, Vector3?)
```
Returns the position and velocity of the target. If the target is a `Vector3`, it only returns the position. If the target is `nil`, both return values will be `nil`.

---
### SetHighPrecision
```lua
InfoCast:SetHighPrecision(value: number)
```
Sets the high precision mode to the given value.

---
### SetTarget
```lua
InfoCast:SetTarget(Target: Vector3 | BasePart | Model | nil)
```
Sets the target to the given value.

!!! info "Remember!"
    The `Model` must have its primary part set; otherwise, an error will occur!

!!! warning "Beware!"
    Setting a new target too frequently can lead to unexpected behaviors!
