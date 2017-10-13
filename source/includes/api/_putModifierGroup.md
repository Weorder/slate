## Modifier group - Update

Change any property or properties of modifier group.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/modifier-groups/11
```

```json
{
    "modifierGroupNo": 11,
    "modifiers": [22, 23, 24, 25]
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/modifier-groups/{modifierGroupNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierGroupNo | integer | true | \d+ | modifier group number
name | string | false | \w+ | name of modifier group
description | string | false | [\w ,-\.] | description of modifier group
type | string | false | ONE / ANY | type (how many modifiers can be chosen)
modifiers | array | false | array of integer | list of related modifiers (modifierNo)

> Response (success)

```json
{
  "status": "success",
  "message": "Modifier group was updated"
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
