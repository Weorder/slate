## Modifier - Update

Update certain properties of modifier.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-group/1/modifier/22
```

```json
{
    "price": 10.5
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/modifiers/{modifierNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | modifier name
price | float | false | | modifier price
description | string | false | | modifier description

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
