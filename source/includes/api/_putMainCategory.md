## Main category - Update 

Change any property or properties of main category.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/menus/101/main-categories/5
```

```json
{
    "mainCategoryNo": 5,
    "name": "Pizza"
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
mainCategoryNo | integer | true | \d+ | main category number
name | string | false | \w+ | name of main category
type | string | false | \w+ | type of main category (see above)
description | string | false | \w+ | description of main category
categories | array | false | array of integer | list of related categories (categoryNo)


> Response (success)

```json
{
  "status": "success",
  "message": "Main category was updated"
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
