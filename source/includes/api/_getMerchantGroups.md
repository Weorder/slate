## Merchant group - Get list

Show already created merchant groups.

> Request (POS -> weorder)

```
HTTP/1.1 GET https://api.weorder.com/pos/v1/merchant-groups
```

### HTTP Request

`HTTP/1.1 GET https://api.weorder.com/pos/v1/merchant-groups`

> Response:

```json
[
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
```

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`

Array of [Merchant group](#merchant-group-create) objects.
