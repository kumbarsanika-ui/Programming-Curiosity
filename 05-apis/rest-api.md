# REST APIs

REST (Representational State Transfer) is an architectural style for networked systems. A REST-style web API commonly represents things as resources identified by URLs and uses HTTP methods to interact with them.

For example, an API might represent a book at `/books/42`. A `GET` request could retrieve it, while a `POST` to `/books` could create a book. The exact design depends on the API's documented contract.

## Useful design ideas

- Give resources clear, consistent names.
- Use HTTP methods and status codes consistently.
- Keep requests self-contained where practical; do not depend on hidden client state.
- Return predictable data formats and clear errors.
- Design authentication, permissions, validation, and rate limits deliberately.

REST is not simply “JSON over HTTP.” JSON is a data format, while REST describes architectural constraints. Many APIs called REST APIs follow some of these ideas without satisfying every formal constraint.

## Safe retries and compatibility

Some methods, such as `GET`, are intended to be safe to repeat without changing server state. Other operations may create or modify data, so a retry can duplicate an action unless the API supports an idempotency mechanism. APIs should also evolve carefully so existing clients do not unexpectedly break.

For the pieces of an exchange, see [Request and response](./request-response.md).
