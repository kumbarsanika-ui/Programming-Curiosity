# HTTP

The Hypertext Transfer Protocol (HTTP) is a set of rules web clients and servers use to exchange requests and responses. A browser is one kind of client; a web server is one kind of service that responds.

## A request and a response

A request includes a method, a target path, headers, and sometimes a body. For example, a browser might send a `GET` request for `/articles`. A response includes a status code, headers, and often a body containing HTML, JSON, an image, or another resource.

Common methods include `GET` to retrieve data, `POST` to submit data or request an action, `PUT` to replace a resource, and `DELETE` to remove one. Their exact semantics matter when designing APIs. Status codes also communicate outcomes: `200` means success, `404` means the requested resource was not found, and `500` indicates a server-side error.

## Stateless by design

HTTP does not automatically remember earlier requests. Applications can use cookies, tokens, or server-side storage to associate requests with a user or session.

## HTTP and security

Plain HTTP does not protect traffic from being read or changed in transit. HTTPS uses HTTP over a protected TLS connection. Use HTTPS for real websites and APIs that handle user data. See [HTTPS](./https.md) and [Request and response](../05-apis/request-response.md).
