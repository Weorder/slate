## Category - Create

Create new category.

> Request (POS -> Snappit)

```
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/mainCategories/5/categories
```

```json
{
    "categoryNo": 10,
    "name": "Pizza from chef",
    "description": "Pizza from chef"
}
```

### HTTP Request

`HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/mainCategories/{mainCategoryNo}/categories'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
categoryNo | integer | true | \d+ | category number
name | string | true | \w+ | name of category
description | string | false | \w+ | description of category

> Response (success)

```json
{
  "status": "success",
  "message": "Category was created"
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
