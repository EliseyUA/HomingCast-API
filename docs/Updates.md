## Update [1.4]  
Date: 27.03.2025  
### Changed names:  
* HighFidelitySegmentSize -> RaysPerMove  
* UseHighPrecision -> HighPrecision  
* PredictionEquation -> Prediction  
* GetAllActiveCast() -> GetAllInfoCast()  

### Optimizations:  
* Fully re-wrote the code for custom trajectory due to its high inefficiency.  
  Now, it's optimized and it's no longer a **`beta feature`**!  

### Deleted:  
* The `distance` setting was deleted from the trajectory plugin.  
* The `Ahead` setting was deleted from the trajectory plugin.  

---  

## Update [1.3]  
Date: 16.03.2025  

### Added new property:  
* Trajectory  
  Currently a **`beta feature`**  

### Added new methods:  
* PauseTrajectory  
* UnPauseTrajectory  
* IsPausedTrajectory  
* SetXscale  
* SetYscale  

### Created new plugin:  
* [Plugin](https://create.roblox.com/store/asset/97281486618608/HomingCast-Plugin)  

### Deleted:  
* `AlignBetweenTargetAndPart` property was deleted and replaced by the `Trajectory` property.  

### `SimulateBeforePhysics` property is enabled  

---  

## Update [1.2]  
Date: 10.03.2025  

### Added new setting:  
```lua
local HomingCast = require(.../HomingCast)  
HomingCast.BatchSize = (number)
```

### Added new function:

* GetAllActiveCast()

### Added new methods:

* SetPosition
* SetDirection
* GetDirection

### Bug fixes:

* Fixed a bug with `UseHighPrecision` property where it didn't work as intended

### `SimulateBeforePhysics` property is temporarily disabled

---

## Update [1.1]
Date: 08.03.2025

### Added new property:

* UseHighPrecision

### Added new methods:

* SetHighPrecision

---