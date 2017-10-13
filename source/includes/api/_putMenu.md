## Menu - Update 

Change any property or properties of menu.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/menus/101
```

```json
{
    "menuNo": 101,
    "name": "Morning menu"
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
menuNo | integer | true | \d+ | menu number
name | string | false | \w+ | name of menu
merchants | array | false | array of integer | list of related merchants (merchantNo)
mainCategories | array | false | array of integer | list of related main categories (mainCategoryNo)


> Response (success)

```json
{
  "status": "success",
  "message": "Menu was updated"
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
