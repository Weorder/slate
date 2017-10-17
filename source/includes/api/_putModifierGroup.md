## Modifier group - Update

Update certain properties of modifier group.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/modifier-groups/11
```

```json
{
    "modifierGroupNo": 11,
    "modifiers": [22, 23, 24, 25]
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/modifier-groups/{modifierGroupNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierGroupNo | integer | true | \d+ | modifier group number
name | string | false | | modifier group name
description | string | false | | modifier group description
type | string | false | ONE / ANY | type (how many modifiers can be chosen)
modifiers | array | false | array of integer | list of related modifiers (modifierNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
