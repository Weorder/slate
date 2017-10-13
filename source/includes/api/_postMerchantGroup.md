## Merchant group - Create

Create merchant group.

> Request (POS -> Snappit)

```
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups
```

```json
{
  "merchantGroupNo": 1,
  "name": "Restaurant group 1",
  "city": "Oslo",
  "timeZone": "Europe/Oslo",
  "supportEmails": [
    "manager1@example.com", 
    "manager2@example.com" 
  ]
}
```

### HTTP Request

`HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
merchantGroupNo | integer | true | \d+ | merchant group number
name | string | true | \w+ | name of merchant group
city | string | false | \w+ | city of merchant group
timeZone | string | false | \w+\/ | timeZone of merchant group
supportEmails | array | false | array of strings | emails of responsible persons

> Response (success)

```json
{
  "status": "success",
  "message": "Merchant group was created"
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
