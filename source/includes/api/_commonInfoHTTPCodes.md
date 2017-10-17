## HTTP Status Codes

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
