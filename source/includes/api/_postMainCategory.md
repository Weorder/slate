## Main category - Create

Create new main category.

> Request (POS -> weorder)

```
HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups/1/menus/101/mainCategories
```

```json
{
    "mainCategoryNo": 5,
    "name": "Food",
    "type": "food",
    "description": "Food menu"
}
```

### HTTP Request

`HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/mainCategories`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
mainCategoryNo | integer | true | \d+ | main category number
name | string | true | | main category name
type | string | false | | main category type (see below)
description | string | false | | main category description

Supported types |
---- |
FOOD |
DRINK |
TICKET |

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
