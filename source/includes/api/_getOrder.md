## Order - Get

Get order from

> Request (POS -> Snappit)

```
HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups/1/merchants/101/orders/10002
```

### HTTP Request

`HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}`

> Response (success)

```json
{
    "status": "success",
    "message": "",
    "data": {
        "orderNo": 1100,
        "menuNo": 111,
        "tip": 15.0,
        "total": 372.0,
        "paymentType": "PAYEX",
        "createdAt": "2017-09-01 09:10",
        "pickupAt": "2017-09-01 10:20",
        "status": "CONFIRMED",
        "customer": {
            "name": "Joe Scooter",
            "phone": "+4710001000"
        },
        "orderLines": [
            {
                "orderLineNo": 12312,
                "articleNo": 23,
                "price": 178.5,
                "quantity": 2,
                "message": "without pepper",
                "modifiers": [17, 20]
            },
            ...
        ],
        "tableNumber": 14,
        "deliveryAddress": "Tordenskiolds gate 6, zip code: 1122",
        "message":"add two pairs of chopsticks"
    }
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
data | object | true | object | order object (see structure - [Order](#order-create-snappit-to-pos))

> Response (success)

```json
{
  "status": "success",
  "message": "Order was created."
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Wrong order number"
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
