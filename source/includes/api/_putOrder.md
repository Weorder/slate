## Order - Update 

Update certain properties of order.

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/merchants/101/orders/1002
```

```json
{
    "orderNo": 10002,
    "pickupAt": "2017-09-01 10:20"
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
orderNo | integer | true | \d+ | order number (in WeOrder)
pickupAt | string | false | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | false | NOT_CONFIRMED / CONFIRMED / DELIVERED /CANCELLED | order status

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
