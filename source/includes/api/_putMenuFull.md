## Menu - Full update

Update menu with all structure (main categories, categories, articles, modifier groups, modifiers).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/menus/101/full
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

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/full'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuNo | integer | true | \d+ | menu number
name | string | false | | menu name
mainCategories | array | true | array of objects | list of [Main category](#main-category-create) objects
mainCategory.categories | array | true | array of objects | list of [Category](#category-create) objects
category.articles | array | true | array of objects | list of [Article](#article-create) objects (except "imageBase64Encode" field)
modifierGroups | array | true | array of objects | list of [Modifier group](#modifier-group-create) objects
modifiers | array | false | array of objects | list of [Modifier](#modifier-create) objects

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
