## Category - Update 

Update certain properties of category.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/menus/101/main-categories/5/categories/10
```

```json
{
    "name": "Pizza from chef (NEW)"
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}/category/{categoryNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | category name
description | string | false | | category description
articles | array | false | array of integer | list of related articles (articleNo). You can use this parameter if you want to set/update relations between category and its articles. The order of passed articles is important and will be used for sorting.

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
