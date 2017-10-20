## Menu - Update 

Update certain properties of menu.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/menus/101
```

```json
{
    "name": "Morning menu"
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | menu name
merchants | array | false | array of integer | list of related merchants (merchantNo)
mainCategories | array | false | array of integer | list of related main categories (mainCategoryNo). You can use this parameter if you want to set/update relations between menu and its main categories. The order of passed main categories is important and will be used for sorting.

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
