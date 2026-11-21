# jwt

Signs and verifies JSON Web Tokens with HS256, HS384, HS512, and EdDSA.

```lus nocheck
local jwt = require("https://atmosp.here/2.0/jwt.lus")

local token = jwt.sign({ sub = "42" }, "secret", { expires_in = 3600 })
local claims = jwt.verify(token, "secret", { algorithms = { "HS256" } })
print(claims.sub)   --> 42
```

The package requires Lus 2.0. It declares no permissions. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `jwt.lus`. Run `lus doc jwt.lus` to print it.
