# Skill communication input/output definition ([Skill name])

**Skill-Name :** `[Name of Skill(e.g. commute)]`

[Description of Skill I/O]

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

[List of all supported proactive types]:

## Proactive types

### [Type name]

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

# Skill I/O Definition (commute)

**Concern-Tag :** `commute`

This skill is all about commute. Additional info should go here.

## General Parameters

None

## Request Types

### Get commute info

**Type-Tag:** `commute_info`

#### Request

No payload

#### Response

- **duration**: [see](#general-parameters)
- **duration_text**: [see](#general-parameters)
- **travel_method**: [see](#general-parameters)
  - "transit"
  - "driving"
  - "bicycling"
  - "walking"

#### Example

Request

```json
{
  "type": "commute_info",
  "payload": {}
}
```

Response

```json
{
  "duration": 83721,
  "duration_text": "5 hours and 25 minutes",
  "travel_method": "transit",
}
```

## Proactive Types

### Commute method update

**Type-Tag:**: `commute_info`

#### Message
- **duration**: [see](#general-parameters)
- **duration_text**: [see](#general-parameters)
- **travel_method**: [see](#general-parameters)
  - "transit"
  - "driving"
  - "bicycling"
  - "walking"

#### Example

```json
{
  "skill": "commute",
  "type": "commute_info",
  "payload": {
    "duration": 83721,
    "duration_text": "5 hours and 25 minutes",
    "travel_method": "transit",
  }
}
```
