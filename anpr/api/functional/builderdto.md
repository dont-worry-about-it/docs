# Builder
- The builder class is a builder pattern used for creating reports.
- Type definitions are available in the `typedefs/anpr.lua`.
- Public Methods:
    - `withReason(reason: string)`: Set a reason for the report (e.g: `Speeding`).
    - `withLicensePlate(plate: string)`: Set a license plate for the suspect vehicle.
    - `withOwner(owner: string)`: Set an owning player (license identifier) for the report (won't be taken into account by the ANPR detections, only there for internal usage).
    - `withColorRange(start: number, end: number)`: Set a primary color range for the suspect vehicle.
    - `withSecondaryColorRange(start: number, end: number)`: Set a secondary color range for the suspect vehicle.
    - `withModel(modelname: string)`: Set a model for the suspect vehicle (e.g: `Adder`).
    - `withManufacturer(manuf: string)`: **NOT USED**, won't affect anything.
- **NOTE**: None of the methods is required the call, and they all return the current instance, so chaining is possible.
### Example:
```lua
return builder:withLicensePlate("kxv-701"):withReason("Speeding"):withColorRange(20, 40)
```