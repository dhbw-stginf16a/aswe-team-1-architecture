# Concern Definition ([Concern Name])

**Concern-Tag :** `[Tag of Concern(e.g. weather)]`

[Description of Concern]

## General Parameters

[List of Parameters needed by many types]

## Request Types

[List of all supported request types]:

### [Type Name]

**Type-Tag:** `[Type Tag]`

#### Request

- **[Parameter1 Name]** ([Parameter1 Type]): [Description]
  - _[Possible Value]_: [Value Description]
- **[Parameter2 Name]**: ([Parameter2 Type]): [Description]

#### Response

- **[Parameter1 Name]** ([Parameter1 Type]): [Description]
  - _[Possible Value]_: [Value Description]
- **[Parameter2 Name]**: ([Parameter2 Type]): [Description]

#### Example

Request

```json
[Example for Request]
```

Response

```json
[Example for Response]
```

[List of all supported subscription Types]:

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

---

Example Definition

# Concern Definition (Weather)

**Concern-Tag :** `weather`

This concern is all about the weather. Additional info should go here.

## General Parameters

- **condition** (string): Describes the weather condition
  - _sun_: The sun is out
  - _rain_: It is raining

## Request Types

### Current Weather

**Type-Tag:** `weather_current`

#### Request

- **location** (string): Name of the city to check the weather for

#### Response

- **condition**: [see](#general-parameters)

#### Example

Request

```json
{
  "type": "weather_current",
  "payload": {
    "location": "Stuttgart"
  }
}
```

Response

```json
{
  "type": "weather_current",
  "payload": {
    "condition": "sun"
  }
}
```

## Subscription Types

### Weather Changed

**Type-Tag:**: `weather_changed`

#### Message

- **location** (string): Name of the city to check the weather for
- **condition**: [see](#general-parameters)
- **old-condition**: _see condition_

#### Example

```json
{
  "type": "weather_changed",
  "payload": {
    "location": "Stuttgart",
    "condition": "sun",
    "old-condition": "rain"
  }
}
```
