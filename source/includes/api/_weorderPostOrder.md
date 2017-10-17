## Order - Create (WeOrder to POS)

Create new order.

<aside class="notice">
POS (which supports public url) must have this method on its side.
</aside>

> Request (WeOrder -> POS)

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
orderNo | integer | true | \d+ | order number (in WeOrder)
menuNo | integer | true | \d+ | menu id in POS (which is used for order)
tip | float | true | | tip for waiters
total | float | true | | order total price
paymentType | string | true | | payment type (see below)
createdAt | string | true | YYYY-MM-DD HH:ii | create order time
pickupAt | string | true | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | true | | order status (see below)
customer | object | true | object | customer data
customer.name | string | true | | customer name
customer.phone | string | true | | customer phone
orderLines | array | true | array of objects | list of order line
orderLine.orderLineNo | integer | true | \d+ | order line number (in WeOrder) 
orderLine.articleNo | integer | true | \d+ | article number (in POS)
orderLine.price | float | true | | price of article with modifiers
orderLine.quantity | integer | true | \d+ | article quantity
orderLine.message | string | false | | additional message for ordered article
orderLine.modifiers | array | false | array of integers | list of chosen modifiers (modifierNo)
tableNumber | integer | false | \d+ | restaurant table number
deliveryAddress | string | false | | delivery address
message | string | false | | additional message for order

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
DELIVERED | order is delivered
CANCELLED | order is cancelled

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`

`Content-Type: application/json`
