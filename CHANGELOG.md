# Changelog

## 1.0.0

**Release date:** TBD

Version 1.0.0 is the first release of `jwt`, which runs on Lus 2.0.

- Added the `jwt` package.
  - `jwt.sign`: Signs a table of claims and returns the token.
  - `jwt.verify`: Verifies a token and returns its claims and its header.
  - `jwt.decode`: Returns the header and the claims of a token without verifying it.
  - `jwt.jwks`: Returns a function that selects the key of a token from a JWKS document.
  - `jwt.iserror`: Returns true for an error object that `jwt` raised.
