## Modifier - Create

Create modifier.

> Request (POS -> Snappit)

```
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/1/modifiers
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

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/modifiers'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierNo | integer | true | \d+ | modifier number
name | string | true | \w+ | name of modifier
price | float | true | \d+\.\d{1-2} | name of modifier
description | string | false | [\w ,-\.] | description of modifier

> Response (success)

```json
{
  "status": "success",
  "message": "Modifier was created"
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
