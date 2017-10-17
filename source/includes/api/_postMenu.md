## Menu - Create

Create new menu.

> Request (POS -> WeOrder)

```
HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/1/menus
```

```json
{
    "menuNo": 101,
    "name": "Weekend menu"
}
```

### HTTP Request

`HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuNo | integer | true | \d+ | menu number
name | string | true | | menu name

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`