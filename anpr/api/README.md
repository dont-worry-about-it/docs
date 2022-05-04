# ANPR API

## API usage
- Our ANPR resource exposes a mostly export driven lua API, but using js/ts is possible for more advanced users.
- Since the resource is written in TypeScript some bugs could occur when passing function references between runtimes (occurs when exports require a callback as an argument, read more [here](#caveats))


## Type definitions
- We expose [EmmyLua](https://emmylua.github.io/) type definitions inside the `typedefs/` folder, without escrowing so you can easily copy it

## Server side Lua exports
- For convenience our [api.lua](https://pastebin.com/8PWcjXs9) is not protected under Cfx escrow, so feel free to look for extra information
- ### Event handler like exports
  - ##### [`onTrigger`](anpr/api/ontrigger.md)
  - ##### [`onReportAdded`](anpr/api/onreportadded.md)
  - *An unlimited amount of handlers can be registered, they will be ran in registration order.*

## Caveats
- When passing a function to an export (mainly for exports starting with `on`)  try to minimize calls to thread yielding functions (`Citizen.Wait`, `Wait` and `CreateThread`). From our experiments, `Citizen.Await` always works, but we are actively investigating for ways to solve this.
- The above problem can be solved by calling an event from the handler since this will switch context to a different thread.