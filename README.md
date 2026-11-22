# jwt

`jwt` signs and verifies JSON Web Tokens with HMAC secrets and with RSA, ECDSA, and Ed25519 keys. It reads keys from PEM text, JSON Web Keys, and JWKS documents. Each key verifies only the algorithms of its own type.

The following example issues a token for a user that expires after an hour, then verifies it.

```lus nocheck
local jwt = require("https://atmosp.here/2.0/jwt.lus")

local token = jwt.sign({ sub = "42" }, "secret", { expires_in = 3600 })
local claims = jwt.verify(token, "secret", { algorithms = { "HS256" } })
print(claims.sub)   --> 42
```

The package requires Lus 2.0 with the RSA and ECDSA keys of `crypto` and declares no permissions. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `jwt.lus`, which `lus doc jwt.lus` prints.
