## Article - Update 

Change any property or properties of article.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/main-categories/5/categories/10/articles/20
```

```json
{
    "articleNo": 20,
    "price": 599.5,
    "modifierGroups": [18, 25]
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}/category/{categoryNo}/articles/{articleNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
articleNo | integer | true | \d+ | article number
name | string | false | \w+ | name of article
price | float | false | \d+\.\d{1-2} | price of article
description | string | false | \w+ | description of article
modifierGroups | array | false | array of integers | list of related modifierGroups (modifierGroupNo)


> Response (success)

```json
{
  "status": "success",
  "message": "Article was updated"
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
