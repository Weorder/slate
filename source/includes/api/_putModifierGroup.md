## Modifier group - Update

Update certain properties of modifier group.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/modifier-groups/11
```

```json
{
    "modifiers": [22, 23, 24, 25]
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/modifier-groups/{modifierGroupNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | modifier group name
description | string | false | | modifier group description
type | string | false | ONE / ANY | type (how many modifiers can be chosen)
modifiers | array | false | array of integer | list of related modifiers (modifierNo). You can use this parameter if you want to set/update relations between modifier group and its modifiers. The order of passed modifiers is important and will be used for sorting.

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
