## Category - Update 

Change any property or properties of category.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/main-categories/5/categories/10
```

```json
{
    "categoryNo": 10,
    "name": "Pizza from chef (NEW)"
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}/category/{categoryNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
categoryNo | integer | true | \d+ | category number
name | string | false | \w+ | name of category
description | string | false | \w+ | description of category
articles | array | false | array of integer | list of related articles (articleNo)


> Response (success)

```json
{
  "status": "success",
  "message": "Category was updated"
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
