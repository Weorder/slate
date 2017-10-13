## Modifier group - Create

Create modifier group.

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/modifier-groups
```

```json
{
    "modifierGroupNo": 11,
    "name": "Additional ingredients for pizza",
    "type": "ANY",
    "description": "Add additional portion of:",
    "modifiers": [22, 23, 24]
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/modifier-groups'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierGroupNo | integer | true | \d+ | modifier group number
name | string | true | \w+ | name of modifier group
type | string | false | ONE / ANY | type (how many modifiers can be chosen)
description | string | false | [\w ,-!:\.\?]  | description of modifier group
modifiers | array | false | array of integer | modifiers list

> Response (success)

```json
{
  "status": "success",
  "message": "Modifier group was created"
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Authentication error. Please call Snappit support team."
}
```

### HTTP Response

`HTTP/1.1 200`

`Content-Type: application/json`

### Response Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
status | string | true | success, error | response status
message | string | true | \w+ | success or error message
