# Configuration
The config is validated at the start of the resource, so if you make any mistakes don't worry the resource won't shit itself. <br>
For an example documentation, see [config.lua](https://pastebin.com/EaXfe87C) (either on the link, or in the resource)

## Config fields
- `locations`: An array of [ANPR configurations](#anpr-sensor-configurations)
- `tickTime`: Defines how often a check cycle is ran (miliseconds) (defaults to `50`)
- `autoRemoveReportsOnHit`: Whether to automatically remove a report from the active reports list if it was detected by an ANPR (if set to `false`, you have to manually remove it using the [API](/anpr/api)) (defaults to `true`)
- `autoJammers `: Whether to make jammers automatically block the detection, regardless of the API output (defaults to `false`)
- `emitClientEventOnHit`: Whether to emit client events to the client which hit the ANPR (can pose security risks, but defaults to `true`)

## ANPR sensor configuration
- `location`: A `vector3` of the position of the ANPR (for realism, it's recommended to set to a higher Z than ground level)
- `name`: A unique name for the ANPR (e.g: `Sandy Shores Main Road`)
- `detectionRange`: The maximum range of detection (in coordinates) (defaults to `50`)
- `canIdentifyByVehDetails`: Whether the ANPR is capable of identifying reports by car model, color range (secondary/primary) (defaults to `true`)
- `isJammable`: Whether the ANPR can be jammed (can be override with [API](/anpr/api) calls) (defaults to `false`)
- `blip`: Whether to display a blip for the ANPR (customizable with the client side [API](/anpr/api)) (defaults to `false`)