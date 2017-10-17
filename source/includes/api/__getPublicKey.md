## Get public key

Get the public key for authentication

### HTTP Request

`HTTP/1.1 GET https://weorder.com/api/pos/get_public_key`

<aside class="notice">
You don't need to pass any headers in this method.
</aside>

> Example

```text
-----BEGIN PUBLIC KEY-----
NGAfMA0GCSqGSIb3DQEBAQUBB4GNADCBiQKBgQC7g2lh6we78LjS5U0rBJ3dMcxb
I/1UTzXJlT/T8OOCmSDWEwpFYISFF3VDIlQjS+3iVOiAylegFQaCoqxXITgXr/BW
TH4tit24htuIyOQs9ppOrg1NtpYIgDJQ6lnqwBNsr5P6wVe0n64NsOBk4CnYPflB
vGq6Z3dMW66ddxgSkwIDAERF
-----END PUBLIC KEY-----
```

### HTTP Response

`HTTP/1.1 200`

`Content-Type: application/octet-stream`
