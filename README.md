# http-server

## Setup
All this setup is neceassary because `ListenAndServeTLS` expects HTTPS connection. 
OpenSSL comes with Mac OS X and Linux. Set up server certificate and private key with: 

```openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout key.pem -out cert.pem```

Important field: `common name`. For localhost at port `8081`: `127.0.0.1:8081`.

## Usage
Run: \
``` go run cmd/main.go```

Example: \
```curl -k https://127.0.0.1:8081/hello```

Need to include `https://` for HTTPS connection, and `-k` to bypass self-signed certificate 
problem.