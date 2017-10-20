## Menu - Get list

Show already created menus for given merchant group.

> Request (POS -> weorder)

```
HTTP/1.1 GET https://api.weorder.com/pos/v1/merchant-group/1/menus
```

### HTTP Request

`HTTP/1.1 GET https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus`

> Response (success):


```json
[
    {
      "menuNo": 21,
      "name": "Main menu"
    },
    ...
]
```

### HTTP Response (success)

`HTTP/1.1 200`

`Content-Type: application/json`

Array of [Menu](#menu-create) objects.
