## Order - Update 

Update certain properties of order.

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/merchants/101/orders/1002
```

```json
{
    "pickupAt": "2017-09-01 10:20"
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
pickupAt | string | false | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | false | | order status. See allowed values in [Order - create](#order-create-weorder-to-pos)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
