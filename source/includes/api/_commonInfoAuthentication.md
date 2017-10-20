## Authentication

> Example on PHP

```php
<?php
    // Necessary parametres:
    //
    // $data = '{"menuNo": 101, ...}';
    // $method = "POST";
    // $url = "https://api.weorder.com/pos/v1/...";
    // $posToken = 'POS token';
    // $privateKey = '-----BEGIN RSA PRIVATE KEY----- ...';
    // $passphrase = 'passphrase for privateKey';
    
    $dataHash = base64_encode(hash('sha256', utf8_encode($data), true));
    $dateUtc = new \DateTime(null, new \DateTimeZone("UTC"));
    $dateUtcString = $dateUtc->format('Y-m-d H:i:s');
    
    $authString = strtoupper($method) . '|' . $url . '|' 
        . 'X-POS-CONTENT-DIGEST=SHA256=' . $dataHash
        . '&X-POS-TOKEN=' . $posToken
        . '&X-POS-TIMESTAMP=' . $dateUtcString;
    $authHash = hash('sha256', $authString, true);
    
    $key = openssl_get_privatekey($privateKey, $passphrase);
    $cryptedAuthHash = ""; // openssl_private_encrypt will put result to $cryptedHash
    openssl_private_encrypt($authHash, $cryptedAuthHash, $key);
    $cryptedAuthHash = base64_encode($cryptedAuthHash);
    
    $headers = [
        'X-POS-Token: ' . $posToken,
        'X-POS-Timestamp: ' . $dateUtcString,
        'X-POS-Content-Digest: SHA256=' . $dataHash,
        'Authorization: RSA-SHA256 ' . $cryptedAuthHash,
    ];
?>
```

Each API request should contain set of headers.

Header | Required? | Description
------ | --------- | -----------
X-POS-Token  | true | POS token
X-POS-Timestamp | true | UTC time in 'Y-m-d H:i:s' format
X-POS-Content-Digest | true | SHA256 of request body
Authorization | true | Signature
