## Setup POS

Setup POS status.

> Request (POS -> Snappit)

```json
{
    "status": "start",
    "menuId": 10
}
```

### HTTP Request

`HTTP/1.1 POST http://snappo.com/api/pos/v1/set_pos_status`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
status | string | true | start / stop | POS status
menuId | integer | false | \d+ | menu id which is used in POS 

"start" - POS initiates start in communication. POS is ready to work.<br/>
"stop" - POS initiates stop in communication. Snappit will not send any requests to POS.

<aside class="notice">
POS will be marked as "started" if Snappit receives some data from POS.<br/>
POS will be marked as "stopped" if Snappit doesn't have success with sending data to POS.
</aside>

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
