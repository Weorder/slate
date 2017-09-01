## Update menu item

Create new menu item or update already existent menu item.

> Request (POS -> Snappit)

```json
{
    "menuId": 201,
    "mainCategoryId": 301,
    "categoryId": 401,
    "item": {
        "id": 111,
        "name": "Small burger",
        "price": 149.95,
        "modifierGroups": [15, 21]
    }
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/update_menu_item`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuId | integer | true | \d+ | menu id in POS
mainCategoryId | integer | true | \d+ | mainCategory id in POS
categoryId | integer | true | \d+ | category id in POS
item | object | true | object | menu item object
item.id | integer | true | \d+ | item id in POS
item.name | string | true | \w+ | name of item
item.price | float | true | \d+\.\d{1-2} | price of item
item.modifierGroups | array | true | array of integers | list of modifier group ids for item

> Response (success)

```json
{
  "status": "success",
  "message": "Menu item is updated"
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Can not find category with given id. Please update entire menu."
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
