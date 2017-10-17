## Merchant - Get list

Show already created merchants for given merchant group.

> Request (POS -> WeOrder)

```
HTTP/1.1 GET https://weorder.com/api/pos/v1/merchant-groups/1/merchants
```

### HTTP Request

`HTTP/1.1 GET https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants`

> Response (success):


```json
[
    {
        "merchantNo": 101,
        "name": "Restaurant 1",
        "address": "Stranden 3",
        "zipCode": "0250",
        "imageUrl": "https://weorder.com/.../restaurant.jpg",
        "menuNo": 21
    },
    ...
]
```

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`

Array of [Merchant](#merchant-create) objects (except "imageBase64Encode" field).
