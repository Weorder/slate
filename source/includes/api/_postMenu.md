## Menu - Create

Create new menu.

> Request (POS -> Snappit)

```
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/1/menus
```

```json
{
    "menuNo": 101,
    "name": "Weekend menu"
}
```

### HTTP Request

`HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuNo | integer | true | \d+ | menu number
name | string | true | \w+ | name of menu

> Response (success)

```json
{
  "status": "success",
  "message": "Menu was created"
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
