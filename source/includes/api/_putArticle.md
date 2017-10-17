## Article - Update 

Update certain properties of article.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/menus/101/main-categories/5/categories/10/articles/20
```

```json
{
    "articleNo": 20,
    "price": 599.5,
    "modifierGroups": [18, 25]
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}/category/{categoryNo}/articles/{articleNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
articleNo | integer | true | \d+ | article number
name | string | false | | article name
price | float | false | | article price
description | string | false | | article description
modifierGroups | array | false | array of integers | list of related modifier groups (modifierGroupNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
