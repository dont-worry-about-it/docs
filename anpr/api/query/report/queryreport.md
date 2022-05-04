# queryReports
#### Usage
```lua
--Promise based
local res = Citizen.Await(exports["ANPR"]:queryDetectionsPromise({by = "licensePlate", queryString = "kxv-701"}))
--Callback based
exports["ANPR"]:queryDetectionsCb({by = "licensePlate", queryString = "kxv-701"}, function(res)
    --do your logic here
end)
```

#### Intrinsics
