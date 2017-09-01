## Set order status

Set order status.

> Request (POS -> Snappit)

```json
{
    "externalId": 111,
    "status": "accepted"
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/set_order_status`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
externalId | integer | true | \d+ | order id in Snappit system
status | string | true | accepted / ready / delivered / cancelled | order status

> Response (success)

```json
{
  "status": "success",
  "message": "Order status is updated."
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Can not accept already cancelled order."
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
