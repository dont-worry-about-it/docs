# onReportAdded
#### Usage:
```lua
exports["ANPR"]:onReportAdded(function(ctx, afterAllHook)
        --do your logic here
        afterAllHook(function(chain)
            --this function will be ran after every middleware was ran
        end)
        return true
    end)
```
### Intrinsics
- A `return true` is **MANDATORY** if you want the report to be registered (if anything else is returned then the report won't get added) 
- Gets called when a new report is added
- The `ctx` parameter is a [`Report`](anpr/api/eventlike/reportdto.md) with the `active` field always being true since the report was just generated (but again, it's not yet registered).
- The function passed to `afterAllHook` will receive an array of the middleware return values (ordered by execution order)
- When the `afterAllHook` functions are ran the report **WILL NOT** be registered yet, but you can't halt the registration anymore. 
- The functions registered with the `onReportAdded` function will be called when a report is being registered (e.g: by calling the [`addReport`](anpr/api/functional/addreport.md) function).