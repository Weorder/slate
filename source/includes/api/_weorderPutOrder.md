## Order - Update (WeOrder to POS)

Update certain properties of order.
If some property is not passed it will be SKIPPED (NOT CHANGED).

<aside class="notice">
POS (which supports public url) must have this method on its side.
</aside>

> Request (WeOrder -> POS)

```
HTTP/1.1 POST https://111.222.111.222/api/v1/merchant-groups/1/merchants/101/orders/10002
```

```json
{
    "orderNo": 10002,
    "pickupAt": "2017-09-01 10:20"
}
```

### HTTP Request

`HTTP/1.1 PUT https://{POS public url}/api/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
orderNo | integer | true | \d+ | order number (in WeOrder)
pickupAt | string | false | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | false | | order status

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`
