## Menu - Delete

Delete menu.

> Request (POS -> Snappit)

```
HTTP/1.1 DELETE https://snappo.com/api/pos/v1/merchant-groups/1/menus/101
```

### HTTP Request

`HTTP/1.1 DELETE https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}`

> Response (success)


```json
{
  "status": "success",
  "message": "Menu was deleted."
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
