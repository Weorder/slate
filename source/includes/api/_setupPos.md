## Setup POS

With this call the POS defines the department and menu to be used.

> Request (POS -> Snappit)

```json
{
    "department": 1,
    "menuId": 10
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/set_pos_status`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
department | integer | true | \d+ | The department to use
menuId     | integer | true | \d+ | menu id which is used in POS 


> Response (success)

```json
{
  "status": "success",
  "message": "POS is marked as started. Snappit uses menu #10."
}
```

> Response (error)

```json
{
  "status": "error",
  "message": "Authorization error. Please call Snappit support team."
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
