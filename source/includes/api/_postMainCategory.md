## Main category - Create

Create new main category.

> Request (POS -> Snappit)

```
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/mainCategories
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

`HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/mainCategories'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
mainCategoryNo | integer | true | \d+ | main category number
name | string | true | \w+ | name of main category
type | string | false | \w+ | type of main category (see below)
description | string | false | \w+ | description of main category

type |
---- |
FOOD |
DRINK |
TICKET |

> Response (success)

```json
{
  "status": "success",
  "message": "Main category was created"
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Authentication error. Please call Snappit support team."
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
