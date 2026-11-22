# AGENTS.md

`lus-lang/atmos-jwt` is the repository of the `jwt` package of the atmosphere registry. Programs load the package with `require("https://atmosp.here/2.0/jwt.lus")`.

## Scope

`jwt` signs and verifies JSON Web Tokens with HMAC secrets and with RSA, ECDSA, and Ed25519 keys. It reads keys from PEM text, JSON Web Keys, and JWKS documents. Each key verifies only the algorithms of its own type. The public API is every function that `jwt.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `jwt.lus` is the whole package. Its header doc comment contains the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load `jwt.lus` from the parent of `TEST_DIR`, the directory that holds the test file.

## Dependencies

- the standard library `crypto` module

## Commands

Run these commands from the root of the repository.

```sh
lus test tests          # run the tests
lus check jwt.lus     # lint
lus doc jwt.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header and in the README.
- Prose follows the `lus-writing` skill, which `lus agents init` installs and https://lus.dev/agents/skills/lus-writing/SKILL.md serves. In particular, prose has no dashes or semicolons and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.
