## Merchant group - Create

Create merchant group.

> Request (POS -> weorder)

```
HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups
```

```json
{
  "merchantGroupNo": 1,
  "name": "Restaurant group 1",
  "city": "Oslo",
  "timeZone": "Europe/Oslo",
  "supportEmails": [
    "manager1@example.com", 
    "manager2@example.com" 
  ]
}
```

### HTTP Request

`HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
merchantGroupNo | integer | true | \d+ | merchant group number
name | string | true | | merchant group name
city | string | false | | merchant group city
timeZone | string | false | | merchant group time zone
supportEmails | array | false | array of strings | emails of responsible persons

Supported time zones |
-------------------- |
Europe/Oslo |
Europe/London |
UTC |

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
