## Common information

> Example

```
HTTP/1.1 GET https://snappo.com/api/pos/v1/merchant-groups`
HTTP/1.1 POST https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/merchants`
HTTP/1.1 PUT https://snappo.com/api/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}`
```

All api methods (POS -> Snappit) start with the following url.

`https://snappo.com/api/pos/v1/...`

All http requests/responses should use valid JSON as request/response body.

Correct MIME media type for JSON is application/json

`Content-Type: application/json`

Simple description of API methods:

Resource | GET | POST | PUT | DELETE
-------- | --- | ---- | --- | ------
/menus | Returns a list of menus (used for certain resources in API v.1) | Create a new menu | Bulk update of menus (skipped in API v.1) | Delete all menus (skipped in API v.1)
/menus/{menuNo} | Returns a specific menu (used for certain resources in API v.1) | Method not allowed (405) | Updates a specific menu | Deletes a specific menu


> Response (success)

```
HTTP/1.1 200
Content-Type: application/json
```

```json
{
  "status": "success",
  "message": "Some message for log. It can be empty."
}
```

> Response (error)

```
HTTP/1.1 401
Content-Type: application/json
```
```json
{
  "status": "error",
  "message": "Authentication error. Please call Snappit support team."
}
```

### Response Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
status | string | true | success, error | response status
message | string | true | \w+ | success or error message
data | array/object | false | array/object | additional data if it is needed (will be described in particular API methods)

### HTTP Status Codes

Codes | Description
----- | -----------
200 (OK) | General success status code. Most common code to indicate success
201 (CREATED) | Successful creation occurred (via either POST or PUT). Set the Location header to contain a link to the newly-created resource. Response body content may or may not be present.
204 (NO CONTENT) | Status when wrapped responses are not used and nothing is in the body (e.g. DELETE).
304 (NOT MODIFIED) | Used in response to conditional GET calls to reduce band-width usage. If used, must set the Date, Content-Location, Etag headers to what they would have been on a regular GET call. There must be no response body.
400 (BAD REQUEST) | General error when fulfilling the request would cause an invalid state. Domain validation errors, missing data, etc. are some examples.
401 (UNAUTHORIZED) | Error code for a missing or invalid authentication token.
403 (FORBIDDEN) | Error code for user not authorized to perform the operation, doesn't have rights to access the resource, or the resource is unavailable for some reason (e.g. time constraints, etc.).
404 (NOT FOUND) | Used when the requested resource is not found, whether it doesn't exist or if there was a 401 or 403 that, for security reasons, the service wants to mask.
409 (CONFLICT) | Whenever a resource conflict would be caused by fulfilling the request. Duplicate entries, deleting root objects when cascade-delete not supported are a couple of examples.
422 (UNPROCESSABLE ENTITY) | Should be used if the server cannot process the enitity, e.g. if an image cannot be formatted or mandatory fields are missing in the payload.
500 (INTERNAL SERVER ERROR) | The general catch-all error when the server-side throws an exception.

