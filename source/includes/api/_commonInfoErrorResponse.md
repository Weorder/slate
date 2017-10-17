## Error Response

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