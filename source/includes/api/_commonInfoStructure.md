## Structure

> Example

```
HTTP/1.1 GET https://api.weorder.com/pos/v1/merchant-groups`
HTTP/1.1 POST https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/merchants`
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}`
```
> Example of successful response:

```
HTTP/1.1 200
Content-Type: application/json
```

```json
[
    {
      "menuNo": 21,
      "name": "Main menu"
    },
    ...
]
```

All api methods (POS -> weorder) start with the following url:

`https://api.weorder.com/pos/v1/...`

All http requests/responses should use valid JSON as request/response body.

Correct MIME media type for JSON is "application/json".

`Content-Type: application/json`

API methods description:

Resource | GET | POST | PUT | DELETE
-------- | --- | ---- | --- | ------
/menus | Returns a list of menus (used for certain resources in API v.1) | Create a new menu | Bulk update of menus (skipped in API v.1) | Delete all menus (skipped in API v.1)
/menus/{menuNo} | Returns a specific menu (used for certain resources in API v.1) | Method not allowed (405) | Updates a specific menu. You can pass only changed properties. | Deletes a specific menu