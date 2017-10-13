## Merchant group - Get list

Show already created merchant groups.

> Request (POS -> Snappit)

```
HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups
```

### HTTP Request

`HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups`

> Response (success)

```json
{
    "status": "success",
    "message": "",
    "data": [
        {
            "merchantGroupNo": 1,
            "name": "Restaurant group 1",
            "city": "Oslo",
            "timeZone": "Europe/Oslo",
            "supportEmails": [
              "manager1@example.com", 
              "manager2@example.com" 
            ]
        },
        ...
    ]
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
data | array | true | array of objects | list of merchant groups (see structure - [Merchant group](#merchant-group-create))
