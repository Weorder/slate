## Merchant group - Update 

Update certain properties of merchant group.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1
```

```json
{
    "supportEmails": [
      "manager1@example.com", 
      "manager2@example.com" 
    ]
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | merchant group name
city | string | false | | merchant group city
timeZone | string | false | | merchant group time zone (see above)
supportEmails | array | false | array of strings | emails of responsible persons
merchants | array | false | array of integer | list of related merchants (merchantNo)
menus | array | false | array of integer | list of related menus (menuNo)

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
