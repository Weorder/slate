## Modifier - Create

Create modifier.

> Request (POS -> WeOrder)

```
HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/1/modifiers
```

```json
{
    "modifierNo": 22,
    "name": "Cheese",
    "price": 10.5,
    "description": "additional 50g of cheese"
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/modifiers`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierNo | integer | true | \d+ | modifier number
name | string | true | | modifier name
price | float | true | | modifier price
description | string | false | | modifier description

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
