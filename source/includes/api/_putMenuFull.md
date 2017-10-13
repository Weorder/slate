## Menu - Full update

Update menu with all structure (main categories, categories, articles, modifier groups, modifiers).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/full
```

```json
{
    "menuNo": 101,
    "name": "September menu",
    "mainCategories": [
        {
            "mainCategoryNo": 1,
            "name": "Food",
            "type": "food",
            "description": "Food menu",
            "categories": [
                {
                    "categoryNo": 10,
                    "name": "Pizza from chef",
                    "description": "Pizza from chef",
                    "articles": [
                        {
                            "articleNo": 27,
                            "name": "4 seasons",
                            "price": 499.5,
                            "description": "It is a variety of pizza in Italian cuisine that is prepared ...",
                            "modifierGroups": [17, 20]
                        },
                        ...
                    ]
                },
                ...
            ]
        },
        ...
    ],
    "modifierGroups": [
        {
            "modifierGroupNo": 11,
            "name": "Additional ingredients for pizza",
            "type": "ANY",
            "description": "Add additional portion of:",
            "modifiers": [22, 23, 24]
        },
        ...
    ],
    "modifiers": [
        {
            "modifierNo": 22,
            "name": "Cheese",
            "price": 10.5,
            "description": "additional 50g of cheese"
        },
        ...
    ]
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/full'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuNo | integer | true | \d+ | menu number
name | string | false | \w+ | menu name
mainCategories | array | true | array of objects | main category list (see structure - [Main category](#main-category-create))
mainCategory.categories | array | true | array of objects | category list (see structure - [Category](#category-create))
category.articles | array | true | array of objects | article list (see structure - [Article](#article-create), except "imageBase64Encode" field)
modifierGroups | array | true | array of objects | modifier group list (see structure - [Modifier group](#modifier-group-create))
modifiers | array | false | array of objects | modifiers list (see structure - [Modifier](#modifier-create))

> Response (success)

```json
{
  "status": "success",
  "message": "Menu was updated"
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Wrong menu structure. Please call Snappit support team."
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
