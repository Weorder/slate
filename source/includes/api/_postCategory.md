## Category - Create

Create new category.

> Request (POS -> WeOrder)

```
HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/1/menus/101/mainCategories/5/categories
```

```json
{
    "categoryNo": 10,
    "name": "Pizza from chef",
    "description": "Pizza from chef"
}
```

### HTTP Request

`HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/mainCategories/{mainCategoryNo}/categories`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
categoryNo | integer | true | \d+ | category number
name | string | true | | category name
description | string | false | | category description

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
