# DetectionQuery

- `by`: `string` Either `date`,  `licensePlate`, `model`, `id`, `playerName`, `playerIdent`, `anprName`. See below for description.
- `queryString`: `string` The string to query by. Supports match patterns specified [here](https://github.com/micromatch/micromatch#matching-features).
- `limit`: `number` The maximum number of entries that can be returned (defaults to `50`).
- `page`: `number` The page id for paginated queries (starts from `1`, defaults to `1`).

## By
- `date`: ISO ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) formatted `string`.
- `licensePlate`: License plate `string`.
- `model`: Vehicle model (e.g: `Adder`).
- `id`: Unique detection id `string` ([UUID V4](https://www.intl-spectrum.com/Article/r848/IS_UUID_V4_UUID_V4_Random_Generation)).
- `playerName`: Player name `string` ([see here](anpr/api/functional/playernameprov.md)).
- `playerIdent`: The FiveM license identifier `string`.
- `anprName`: The name of the ANPR as specified in the [config](anpr/config.md)
- **The query string for each strategy has to go into the `queryString` parameter, as a `string`.**
- **Pattern matching is supported for every key (read more [here](https://github.com/micromatch/micromatch#matching-features)).**