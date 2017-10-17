## Menu - Update 

Update certain properties of menu.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/menus/101
```

```json
{
    "menuNo": 101,
    "name": "Morning menu"
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuNo | integer | true | \d+ | menu number
name | string | false | | menu name
merchants | array | false | array of integer | list of related merchants (merchantNo)
mainCategories | array | false | array of integer | list of related main categories (mainCategoryNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
