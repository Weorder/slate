## Merchant - Update 

Update certain properties of merchant.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> WeOrder)

```
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/1/merchants/101
```

```json
{
    "merchantNo": 101,
    "name": "Restaurant 1",
    "address": "Stranden 3",
    "zipCode": "0250",
    "imageUrl": "https://pos.com/restaurant.jpg",
    "imageBase64Encode": "",
    "menuNo": 21
}
```

### HTTP Request

`HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
merchantNo | integer | true | \d+ | merchant number
name | string | false | | merchant name
address | string | false | | merchant address 
zipCode | string | false | \d+ | merchant zip code
imageUrl | string | false | | image url
imageBase64Encode | string | false | | base64 encoded image
menuNo | string | false | \d+ | menu number

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
