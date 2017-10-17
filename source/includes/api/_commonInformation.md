## Common information

> Example

```
HTTP/1.1 GET https://weorder.com/api/pos/v1/merchant-groups`
HTTP/1.1 POST https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants`
HTTP/1.1 PUT https://weorder.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}`
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

All api methods (POS -> WeOrder) start with the following url:

`https://weorder.com/api/pos/v1/...`

All http requests/responses should use valid JSON as request/response body.

Correct MIME media type for JSON is "application/json".

`Content-Type: application/json`

API methods description:

Resource | GET | POST | PUT | DELETE
-------- | --- | ---- | --- | ------
/menus | Returns a list of menus (used for certain resources in API v.1) | Create a new menu | Bulk update of menus (skipped in API v.1) | Delete all menus (skipped in API v.1)
/menus/{menuNo} | Returns a specific menu (used for certain resources in API v.1) | Method not allowed (405) | Updates a specific menu | Deletes a specific menu

> Example of error response:

```
HTTP/1.1 401
Content-Type: application/json
```
```json
{
  "message": "Authorization error. Please contact support team."
}
```

### Error Response Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
message | string | true | | error message

### HTTP Status Codes

Codes | Description
----- | -----------
200 OK | General success status code. Most common code to indicate success
201 Created | Successful creation occurred (via either POST or PUT). Response body content may or may not be present.
204 No Content | Status when wrapped responses are not used and nothing is in the body (e.g. DELETE).
304 Not Modified | Used in response to conditional GET calls to reduce band-width usage. If used, must set the Date, Content-Location, Etag headers to what they would have been on a regular GET call. There must be no response body.
400 Bad Request | General error when fulfilling the request would cause an invalid state. Domain validation errors, missing data, etc. are some examples.
401 Unauthorized | Error code for a missing or invalid authorization token.
403 Forbidden | Error code for user not authorized to perform the operation, doesn't have rights to access the resource, or the resource is unavailable for some reason (e.g. time constraints, etc.).
404 Not Found | Used when the requested resource is not found, whether it doesn't exist or if there was a 401 or 403 that, for security reasons, the service wants to mask.
405 Method Not Allowed | A request method is not supported for the requested resource.
409 Conflict | Whenever a resource conflict would be caused by fulfilling the request. Duplicate entries, deleting root objects when cascade-delete not supported are a couple of examples.
500 Internal Server Error | The general catch-all error when the server-side throws an exception.
501 Not Implemented | Feature of a web-service API which is not implemented yet.
