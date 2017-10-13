## Order - Create (Snappit to POS)

Create new order.

<aside class="notice">
POS (which supports public url) must have this method on its side.
</aside>

> Request (Snappit -> POS)

```
HTTP/1.1 POST https://111.222.111.222/api/v1/merchant-groups/1/merchants/101/orders
```

```json
{
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
```

### HTTP Request

`HTTP/1.1 POST https://{POS public url}/api/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
orderNo | integer | true | \d+ | order number (in Snappit)
menuNo | integer | true | \d+ | menu id in POS (which is used for order)
tip | float | true | \d+\.\d{1-2} | tip for waiters
total | float | true | \d+\.\d{1-2} | total price of order
paymentType | string | true | \w+_ | payment type (see below)
createdAt | string | true | YYYY-MM-DD HH:ii | create order time
pickupAt | string | true | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | true | \w+_ | status of order (see below)
customer | object | true | object | customer data
customer.name | string | true | \w+ | name of customer
customer.phone | string | true | \w+ | phone of customer
orderLines | array | true | array of objects | order line list
orderLine.orderLineNo | integer | true | \d+ | order line number (in Snappit) 
orderLine.articleNo | integer | true | \d+ | article number (in POS)
orderLine.price | float | true | \d+\.\d{1-2} | price of article with modifiers
orderLine.quantity | integer | true | \d+ | quantity of article
orderLine.message | string | false | \w+ | additional message for ordered article
orderLine.modifiers | array | false | array of integers | list of chosen modifier ids
tableNumber | integer | false | \d+ | restaurant table number
deliveryAddress | string | false | \w+ | delivery address
message | string | false | \w+ | additional message for order

Payment type | Description
------------ | ----------- 
AT_PICKUP | means pay at pickup or delivery
PAYEX | payment system
VIPPS | payment system
BAMBORA | payment system
KLARNA | not implemented yet
MOBILE_PAY | payment system
CASH_POINTS | means order was payed by accumulated cash points
EPAY | not implemented yet

Status | Description
------------ | ----------- 
NOT_CONFIRMED | order is not confirmed by waiter
CONFIRMED | order is confirmed by waiter
DELIVERED | order is delivered
CANCELLED | order is cancelled

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
  "message": "Wrong customer information"
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
