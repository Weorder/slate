## Merchant - Get list

Show already created merchants for given merchant group.

> Request (POS -> Snappit)

```
HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups/1/merchants
```

### HTTP Request

`HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants`

> Response (success)


```json
{
    "status": "success",
    "message": "",
    "data": [
        {
            "merchantNo": 101,
            "name": "Restaurant 1",
            "address": "Stranden 3",
            "zipCode": "0250",
            "imageUrl": "https://snappo.com/.../restaurant.jpg",
            "menuNo": 21
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
data | array | true | array of objects | list of merchant (see structure - [Merchant](#merchant-create), except "imageBase64Encode" field)
