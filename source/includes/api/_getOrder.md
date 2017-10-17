## Order - Get

Get order.

> Request (POS -> WeOrder)

```
HTTP/1.1 GET https://weorder.com/api/pos/v1/merchant-groups/1/merchants/101/orders/10002
```

### HTTP Request

`HTTP/1.1 GET https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}`

> Response:

```json
{
    "orderNo": 1100,
    "menuNo": 111,
    "tip": 15,
    "total": 372,
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
```

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`

Returns  [Order](#order-create-weorder-to-pos) object.
