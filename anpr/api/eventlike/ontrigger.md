# onTrigger
#### Usage:
```lua
exports["ANPR"]:onTrigger(function(ctx, afterAllHook)
        --do your logic here
        afterAllHook(function(chain)
            --this function will be ran after every middleware was ran
        end)
        return true
    end)
```
### Intrinsics
- A `return true` is **MANDATORY** if you want the ANPR to register the detection (if anything else is returned then the ANPR report will not fire and the report will stay active) 
- Gets called when an ANPR finds a matching report for a certain vehicle (if the player had a jammer and the `autoJammers` config field is set to `true` then the detection halts immediately so the functions **WILL NOT** be ran)
- The `ctx` parameter is a [`TriggerCtx`](anpr/api/eventlike/triggerdto.md)
- Using the `afterAllHook` is not mandatory, and the return value of the passed function will be ignored.
- The function passed to `afterAllHook` will receive an array of the middleware return values (ordered by execution order)
- When the `afterAllHook` functions are ran the detection **WILL NOT** be registered yet, but you can't halt the registration anymore. 