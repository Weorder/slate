## Updates - Fetch list

Fetch list of updates (orders which have been changed)

<aside class="notice">
For POS which doesn't support public url
</aside>

> Request (POS -> WeOrder)

```
HTTP/1.1 POST https://weorder.com/api/pos/v1/updates
```

```json
{
    "updateNo": 100,
    "limit": 50,
    "types": ["NEW_ORDER", "ORDER_UPDATE"]
}
```

### HTTP Request

`HTTP/1.1 POST https://weorder.com/api/pos/v1/updates`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
updateNo | integer | false | \d+ | Identifier of the first update to be returned. Must be greater by one than the highest among the identifiers of previously received updates. By default, updates starting with the earliest unconfirmed update are returned. An update is considered confirmed as soon as "/updates" is called with an offset higher than its updateNo. All previous updates will be forgotten.
limit | integer | false | \d+ | Limits the number of updates to be retrieved. Values between 1—100 are accepted. Default is 100.
types | array | false | array of string | List the types of updates you want to receive. Specify an empty list to receive all updates regardless of type (default).

Type      | Description
--------- | ------------
NEW_ORDER | new order with structure
ORDER_UPDATE | update of specific fields of order

> Response:

```json
[
    {
        "updateNo": 100,
        "type": "ORDER_UPDATE",
        "data": {
            "orderNo": 10000,
            "pickupAt": "2017-09-01 10:20"
        }
    },
    {
        "updateNo": 101,
        "type": "ORDER_UPDATE",
        "data": {
            "orderNo": 10001,
            "status": "CANCELLED"
        }
    },        
    {
        "updateNo": 102,
        "type": "NEW_ORDER",
        "data": {
            "orderNo": 10002,
            "menuNo": 111,
            "tip": 15,
            "total": 372,
            "paymentType": "Payex",
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
    },
    ...
    
]
```

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`

### Response Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
updates | array | true | array of objects | list of updates
update.updateNo | integer | true | \d+ | update number
update.type | string | true | \w+ | update type
update.data | object | true | object | object according to the type
 
Supported type | Object
-------------- | ------------
NEW_ORDER | [Order](#order-create-weorder-to-pos) object
ORDER_UPDATE | [Order - Update](#order-update-weorder-to-pos) object
