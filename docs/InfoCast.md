## What is InfoCast?

InfoCast is a modified version of [Caster](Caster.md). It contains all properties, the current position, direction, reference to the `Caster`, etc.

---
### Where do I get InfoCast?

InfoCast is returned in all 5 signals. Read more about it [here](Caster.md).

Additionally, when you start a simulation using:

```lua
local InfoCast = Caster:Fire(...)
```

You will receive an `InfoCast`.

---
### Retrieving all active InfoCast

You can retrieve all currently simulated `InfoCast` using the function `HomingCast.GetAllInfoCast()`:

```lua
local HomingCast = require(.../HomingCast)

local TableOfInfoCast: {} = HomingCast.GetAllInfoCast() -- Returns a table containing all active InfoCast
```

This function returns a table containing all active `InfoCast` that are currently being simulated.