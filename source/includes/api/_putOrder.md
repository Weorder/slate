## Order - Update 

Change certain properties of order.

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/merchants/101/orders/1002
```

```json
{
    "orderNo": 10002,
    "pickupAt": "2017-09-01 10:20"
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}/orders/{orderNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
orderNo | integer | true | \d+ | order number (in Snappit)
pickupAt | string | false | YYYY-MM-DD HH:ii | pickup or delivery time
status | string | false | NOT_CONFIRMED / CONFIRMED / DELIVERED /CANCELLED | status of order

> Response (success)

```json
{
  "status": "success",
  "message": "Order was updated"
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Authentication error. Please call Snappit support team."
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
