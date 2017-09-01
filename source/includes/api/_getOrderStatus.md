## Get order status (Snappit -> POS)

Get order status.

> Request (Snappit -> POS)

```json
{
    "externalId": 111
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/get_order_status`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
externalId | integer | true | \d+ | order id in Snappit system

> Response (success)

```json
{
    "status": "success",
    "message": "",
    "order":
    {
        "externalId": 111,
        "status": "accepted"
    }
}
```

> Response (error)

```json
{
    "status": "error",
    "message": "Can not found order by given id."
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
order | object | false | object | order object
order.externalId | integer | true | \d+ | order id in Snappit system
order.status | string | true | accepted / ready / delivered / cancelled | order status

