## Menu - Get list

Show already created menus for given merchant group.

> Request (POS -> Snappit)

```
HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-group/1/menus
```

### HTTP Request

`HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus`

> Response (success)


```json
{
    "status": "success",
    "message": "",
    "data": [
        {
          "menuNo": 21,
          "name": "Main menu"
        },
        ...
    ]
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
data | array | true | array of objects | list of menus (see structure - [Menu](#menu-create))
