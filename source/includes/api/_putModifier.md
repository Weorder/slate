## Modifier - Update

Change any property or properties of modifier.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-group/1/modifier/22
```

```json
{
    "modifierNo": 22,
    "price": 10.5
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/modifiers/{modifierNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierNo | integer | true | \d+ | modifier number
name | string | false | \w+ | name of modifier
price | float | false | \d+\.\d{1-2} | name of modifier
description | string | false | [\w ,-!:\.\?] | description of modifier

> Response (success)

```json
{
  "status": "success",
  "message": "Modifier was updated"
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
