## Article - Create

Create new article.

> Request (POS -> Snappit)

```
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/mainCategories/5/categories/10/articles
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

`HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/mainCategories/{mainCategoryNo}/categories/{categoryNo}/articles'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
articleNo | integer | true | \d+ | article number
name | string | true | \w+ | name of article
price | float | true | \d+\.\d{1-2} | price of article
description | string | false | \w+ | description of article
modifierGroups | array | false | array of integers | list of related modifier groups (modifierGroupsNo)

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
