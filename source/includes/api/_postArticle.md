## Article - Create

Create new article.

> Request (POS -> WeOrder)

```
HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/1/menus/101/mainCategories/5/categories/10/articles
```

```json
{
    "articleNo": 20,
    "name": "4 seasons",
    "price": 499.5,
    "description": "It is a variety of pizza in Italian cuisine that is prepared ...",
    "modifierGroups": [17, 20]
}
```

### HTTP Request

`HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/mainCategories/{mainCategoryNo}/categories/{categoryNo}/articles`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
articleNo | integer | true | \d+ | article number
name | string | true | | article name
price | float | true | | article price
description | string | false | | article description
modifierGroups | array | false | array of integers | list of related modifier groups (modifierGroupsNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
