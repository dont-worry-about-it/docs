# addReport

#### Usage:
```lua
 local reportId = exports["ANPR"]:addReport(function(builder) --builder like pattern
        return builder:withLicensePlate(plate):withReason("license plate based detection test")
    end)
```

#### Intrinsics
- The function passed to `addReport` has to return the `builder` parameter.
- The builder parameter is an instance of [Builder](anpr/api/functional/builderdto.md).
- The return value of the API will be a report ID unique to this report ([UUID V4](https://www.intl-spectrum.com/Article/r848/IS_UUID_V4_UUID_V4_Random_Generation)).
- Before the report finally gets registered, the handlers registered with [`onReportAdded`](anpr/api/eventlike/onreportadded.md) will be called.