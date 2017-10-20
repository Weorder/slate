## Merchant - Create

Create new merchant.

> Request (POS -> weorder)

```
HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups/1/merchants
```

```json
{
    "merchantNo": 101,
    "name": "Restaurant 1",
    "address": "Stranden 3",
    "zipCode": "0250",
    "imageUrl": "https://pos.com/restaurant.jpg",
    "menuNo": 21
}
```

### HTTP Request

`HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/merchants`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
merchantNo | integer | true | \d+ | merchant number
name | string | true | | merchant name
address | string | false | | merchant address 
zipCode | string | false | | merchant zip code
imageUrl | string | false | | image url
imageBase64Encode | string | false | | base64 encoded image
menuNo | integer | false | \d+ | menu number

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
