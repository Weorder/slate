## Update menu

Create new menu or update already existent menu.

> Request (POS -> Snappit)

```json
{
    "id": 301,
    "name": "September menu",
    "mainCategories": [
        {
            "id": 1,
            "name": "Food",
            "categories": [
                {
                    "id": 11,
                    "name": "Burgers",
                    "items": [
                        {
                            "id": 111,
                            "name": "Small burger",
                            "price": 149.95,
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
            "id": 17,
            "name": "Extra portion",
            "modifiers": [
                {
                    "id": 31,
                    "name": "Cheese",
                    "price": 19.95
                },
                ...
            ]
        },
        ...
    ]
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/update_menu`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
id | integer | true | \d+ | menu id in POS
name | string | false | \w+ | menu name
mainCategories | array | true | array of objects | main category list
mainCategory.id | integer | true | \d+ | main category id in POS
mainCategory.name | string | true | \w+ | name of main category
mainCategory.categories | array | true | array of objects | category list
category.id | integer | true | \d+ | category id in POS
category.name | string | true | \w+ | name of category
category.items | array | true | array of objects | item list
item.id | integer | true | \d+ | item id in POS
item.name | string | true | \w+ | name of item
item.price | float | true | \d+\.\d{1-2} | price of item
item.modifierGroups | array | true | array of integers | list of modifier group ids for item
modifierGroups | array | true | array of objects | modifier group list
modifierGroup.id | integer | true | \d+ | modifier group id in POS
modifierGroup.name | string | true | \w+ | name of modifier group
modifierGroup.modifiers | array | true | array of objects | modifiers list
modifier.id | integer | true | \d+ | modifier id in POS
modifier.name | string | true | \w+ | name of modifier
modifier.price | float | true | \d+\.\d{1-2} | price of modifier

> Response (success)

```json
{
  "status": "success",
  "message": "Menu is updated"
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
