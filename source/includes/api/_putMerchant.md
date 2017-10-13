## Merchant - Update 

Change any property or properties of merchant.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> Snappit)

```
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/1/merchants/101
```

```json
{
    "merchantNo": 101,
    "name": "Restaurant 1",
    "address": "Stranden 3",
    "zipCode": "0250",
    "imageUrl": "http://pos.com/restaurant.jpg",
    "imageBase64Encode": "",
    "menuNo": 21
}
```

### HTTP Request

`HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants/{merchantNo}'

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
merchantNo | integer | true | \d+ | merchant number
name | string | false | \w+ | name of merchant
address | string | false | [\w ,-\.] | address of merchant 
zipCode | string | false | \d+ | zipCode of merchant
imageUrl | string | false | string | image url, pass imageUrl or imageBase64
imageBase64Encode | string | false | string | image url, pass imageUrl or imageBase64
menuNo | string | false | \d+ | menu number

> Response (success)

```json
{
  "status": "success",
  "message": "Merchant was updated"
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
