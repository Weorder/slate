## Create order (Snappit -> POS)

Update order status.

> Request (Snappit -> POS)

```json
{
    "externalId": 123,
    "menuId": 111,
    "tableNumber": 14,
    "tip": 15.0,
    "total": 372.0,
    "prePaid": true,
    "paymentType": "Payex",
    "createdAt": "2017-09-01 09:10",
    "pickupAt":"2017-09-01 10:20",
    "deliveryAddress":"Tordenskiolds gate 6",
    "customerName":"Joe Scooter",
    "customerPhone":"+4710001000",
    "message":"add two pairs of chopsticks",
    "orderLines": [
        {
            "id": 23,
            "price": 178.5,
            "quantity": 2,
            "message": "without pepper",
            "modifiers": [17, 20]
        },
        ...
    ]
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/create_order`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
externalId | integer | true | \d+ | order id in Snappit system
menuId | integer | true | \d+ | menu id in POS (which is used for order)
tableNumber | integer | false | \d+ | restaurant table number
tip | float | true | \d+\.\d{1-2} | tip for waiters
total | float | true | \d+\.\d{1-2} | total price of order
prePaid | boolean | true | true / false | is order prepaid?
paymentType | string | false | \w+ | payment type as string
deliveryAddress | string | false | \w+ | delivery address
createdAt | string | true | YYYY-MM-DD HH:ii | create order time
pickupAt | string | true | YYYY-MM-DD HH:ii | pickup or delivery time
customerName | string | true | \w+ | name of customer
customerPhone | string | true | \w+ | phone of customer
message | string | false | \w+ | additional message for order
orderLines | array | true | array of objects | order line list
orderLine.id | integer | true | \d+ | item id in POS
orderLine.price | float | true | \d+\.\d{1-2} | price of item with modifiers
orderLine.quantity | integer | true | \d+ | count of item
orderLine.message | string | false | \w+ | additional message for ordered item
orderLine.modifiers | array | false | array of integers | list of chosen modifier ids

> Response (success)

```json
{
  "status": "success",
  "message": "Order is created."
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Wrong menu version"
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
