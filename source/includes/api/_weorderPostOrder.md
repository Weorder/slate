## Order - Create (weorder to POS)

Create new order.

<aside class="notice">
POS (which supports public url) must have this method on its side.
</aside>

> Request (weorder -> POS)

```
HTTP/1.1 POST https://111.222.111.222/api/v1/merchant-groups/1/merchants/101/orders
```

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
    "tableNumber": 14,
    "deliveryAddress": "Tordenskiolds gate 6, zip code: 1122",
    "message":"add two pairs of chopsticks",
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
    ]
}
```

### HTTP Request

`HTTP/1.1 POST https://{POS public url}/api/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
orderNo | integer | true | \d+ | order number (in weorder)
menuNo | integer | true | \d+ | menu id in POS (which is used for order)
tip | float | true | | tip for waiters
total | float | true | | order total price
paymentType | string | true | | payment type (see below)
createdAt | string | true | YYYY-MM-DD HH:ii | create order time
pickupAt | string | true | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | true | | order status (see below)
tableNumber | integer | false | \d+ | restaurant table number
deliveryAddress | string | false | | delivery address
message | string | false | | additional message for order
customer | object | true | object | customer data  (see below)
orderLines | array | true | array of objects | list of order lines  (see below)

Payment type | Description
------------ | ----------- 
AT_PICKUP | means pay at pickup or delivery
CASH_POINTS | means order was payed by accumulated cash points
PAYEX | 
VIPPS | 
BAMBORA | 
EPAY |

Status | Description
------------ | ----------- 
NOT_CONFIRMED | order is not confirmed by waiter
CONFIRMED | order is confirmed by waiter
READY_FOR_PICKUP | order is ready for pickup
DELIVERED | order is delivered
CANCELLED | order is cancelled

Customer parameters | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | true | | customer name
phone | string | true | | customer phone

Order line parameters | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
orderLineNo | integer | true | \d+ | order line number (in weorder) 
articleNo | integer | true | \d+ | article number (in POS)
price | float | true | | price of article with modifiers
quantity | integer | true | \d+ | article quantity
message | string | false | | additional message for ordered article
modifiers | array | false | array of integers | list of chosen modifiers (modifierNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`

`Content-Type: application/json`
