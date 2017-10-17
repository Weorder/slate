## Category - Update 

Update certain properties of category.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/menus/101/main-categories/5/categories/10
```

```json
{
    "categoryNo": 10,
    "name": "Pizza from chef (NEW)"
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}/category/{categoryNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
categoryNo | integer | true | \d+ | category number
name | string | false | | category name
description | string | false | | category description
articles | array | false | array of integer | list of related articles (articleNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
