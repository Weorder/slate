## Article - Update 

Update certain properties of article.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/menus/101/main-categories/5/categories/10/articles/20
```

```json
{
    "price": 599.5,
    "imageUrl": "https://pos.com/images/article20.jpg",
    "modifierGroups": [18, 25]
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}/category/{categoryNo}/articles/{articleNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | article name
price | float | false | | article price
description | string | false | | article description
imageUrl | string | false | | image url
imageBase64Encode | string | false | | base64 encoded image
modifierGroups | array | false | array of integers | list of related modifier groups (modifierGroupNo). You can use this parameter if you want to set/update relations between article and its modifier groups. The order of passed modifier groups is important and will be used for sorting.

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
