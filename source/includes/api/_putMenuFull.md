## Menu - Full update

Update menu with all structure (main categories, categories, articles, modifier groups, modifiers).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/menus/101/full
```

```json
{
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

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/full`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | menu name
mainCategories | array | true | array of objects | list of [Main category](#main-category-create) objects. Object must contain mainCategoryNo, name fields. Other fields are not required.
categories | array | true | array of objects | list of [Category](#category-create) objects. Object must contain categoryNo, name fields. Other fields are not required.
articles | array | true | array of objects | list of [Article](#article-create) objects. Object must contain articleNo, name, price fields. Other fields are not required. ImageBase64Encode field is not allowed here.
modifierGroups | array | false | array of objects | list of [Modifier group](#modifier-group-create) objects. Object must contain modifierGroupNo, name fields. Other fields are not required.
modifiers | array | false | array of objects | list of [Modifier](#modifier-create) objects. Object must contain modifierNo, name, price fields. Other fields are not required. 

<aside class="notice">
    The order of passed objects or object numbers is important and will be used for sorting.
</aside>

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
