# Skill communication input/output definition ([preferences])

**Skill-Name :** `preferences`

[Description of Skill I/O]

## General Parameters

[List of Parameters needed by many types]

## Request Types

[List of all supported request types]:

### Set user preferences

**Type-Tag:** `set_user_prefs`

#### Request

The affected user will be determined by the `user_handle` and `input_service` handle.
The entire payload is a flat object with preferences to update.

#### Response

- **success** (bool): Whether the operation was successful

#### Example

Request

```json
{
  "type": "set_user_prefs",
  ...,
  "payload": {
    "name": "Emil Zeiger",
    "home_address": "Sachsen"
  }
}
```

Response

```json
{
  "success": true
}
```

### Get user preferences

**Type-Tag:** `get_user_prefs`

#### Request

The affected user will be determined by the `user_handle` and `input_service` handle.

- **keys** (array->string): The keys to query. Unknown keys are ignored. If left empty, all known entries will be returned.

#### Response

The payload is an object containing preference key to value mappings.

#### Example

Request

```json
{
  "type": "get_user_prefs",
  "payload": {
    "keys": [ "name" ]
  }
}
```

Response

```json
{
  "name": "Emil Zeiger"
}
