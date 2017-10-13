## Merchant group - Update 

Change any property or properties of merchant group.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1
```

```json
{
    "merchantGroupNo": 1,
    "supportEmails": [
      "manager1@example.com", 
      "manager2@example.com" 
    ]
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
merchantGroupNo | integer | true | \d+ | merchant group number
name | string | false | \w+ | name of merchant group
city | string | false | \w+ | city of merchant group
timeZone | string | false | \w+\/ | timeZone of merchant group
supportEmails | array | false | array of strings | emails of responsible persons
merchants | array | false | array of integer | list of related merchants (merchantNo)
menus | array | false | array of integer | list of related menus (menuNo)

> Response (success)

```json
{
  "status": "success",
  "message": "Merchant group was updated"
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
