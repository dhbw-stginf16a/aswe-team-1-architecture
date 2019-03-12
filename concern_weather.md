# Concern Weather

**Concern-Tag :** `weather`

This concern is all about weather. It is dependent upon openweathermap.com.
It is possible to request the current weather data and a forecast for the next 5 days in 3 hour intervals

## General Parameters

- ** location ** (String): Specifies the location to query
  - _{city name},{country code}_: Specify the city name and probably the country code de (for example `"Suttgart,de"`)
  - _{zip code},{country code}_: Specify the country name and the country code (for example `"04516,de"`)

- ** condition.id ** (Integer): Identifier to not math strings
  - _TBD_: either plain from [here](https://openweathermap.org/weather-conditions) or a little bit condensed

- ** condition.description ** (String): Describes the weather in one word
  - [adjectives](https://openweathermap.org/weather-conditions)

- ** temp ** (Float): Temperature in Degrees

- ** data ** (JSON): Data dump from the API in the form found at either [here](https://openweathermap.org/current#current_JSON) or [here](https://openweathermap.org/forecast5#JSON)
## Request Types

[List of all supported request types]:

### current weather dump

**Type-Tag:** `weather_current`

#### Request

- **location** (String): [see](#general-parameters)

#### Response

- **data** (JSON): of type 1[Description]

#### Example

Request

```json
{
  "type": "weather_current",
  "payload": {
    "location": "Stuttgart,de"
  }
}
```

Response

```json
{
  "type": "weather_current",
  "payload": {
    "data": {
      "coord": {"lon":145.77,"lat":-16.92},
      "weather": [{"id":803,"main":"Clouds","description":"broken clouds","icon":"04n"}],
      "base":"cmc stations",
      "main":{"temp":293.25,"pressure":1019,"humidity":83,"temp_min":289.82,"temp_max":295.37},
      "wind":{"speed":5.1,"deg":150},
      "clouds":{"all":75},
      "rain":{"3h":3},
      "dt":1435658272,
      "sys":{"type":1,"id":8166,"message":0.0166,"country":"AU","sunrise":1435610796,"sunset":1435650870},
      "id":2172797,
      "name":"Cairns",
      "cod":200
    }
  }
}
```

### current weather brief TBD

**Type-Tag:** `weather_current_TBD`
Currenctly not implemented has to be specified for further use

#### Request

- **location** (String): [Description]

#### Response

- **conditions** (array of conditions): [Description]
- **temp** (Float): [Description]

#### Example

Request

```json
{
  "type": "weather_current",
  "payload": {
    "location": "Stuttgart,de"
  }
}
```

Response

```json
{
  "type": "weather_current",
  "payload": {
    "conditions": {
      /*TODO*/
    }
  }
}
```

## Subscription Types

### [Type Name]

**Type-Tag:** `[Type Tag]`

#### Message

- **[Parameter1 Name]** ([Parameter1 Type]): [Description]
  - _[Possible Value]_: [Value Description]
- **[Parameter2 Name]**: ([Parameter2 Type]): [Description]

#### Example

```json
[Example for message]
```
