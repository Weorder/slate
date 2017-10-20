## Order - Update (weorder to POS)

Update certain properties of order.
If some property is not passed it will be SKIPPED (NOT CHANGED).

<aside class="notice">
POS (which supports public url) must have this method on its side.
</aside>

> Request (weorder -> POS)

```
HTTP/1.1 POST https://111.222.111.222/api/v1/merchant-groups/1/merchants/101/orders/10002
```

```json
{
    "pickupAt": "2017-09-01 10:20"
}
```

### HTTP Request

`HTTP/1.1 PUT https://{POS public url}/api/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
pickupAt | string | false | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | false | | order status. See allowed values in [Order - create](#order-create-weorder-to-pos)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`
