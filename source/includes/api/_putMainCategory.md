## Main category - Update 

Update certain properties of main category.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/menus/101/main-categories/5
```

```json
{
    "mainCategoryNo": 5,
    "name": "Pizza"
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
mainCategoryNo | integer | true | \d+ | main category number
name | string | false | | main category name
type | string | false | | main category type (see above)
description | string | false | | main category description
categories | array | false | array of integer | list of related categories (categoryNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
