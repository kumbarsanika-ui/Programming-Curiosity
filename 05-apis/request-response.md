# Request and response

Many web APIs work through a request-response exchange: a client asks a server to do something or provide information, and the server returns a result.

## What goes in a request?

A request commonly contains:

- A method describing the kind of operation, such as `GET` or `POST`.
- A URL identifying the server and resource.
- Headers containing metadata, such as the expected content format.
- An optional body containing submitted data, often JSON.

Example JSON body:

```json
{
  "productId": 42,
  "quantity": 2
}
```

The server should validate incoming data rather than assume it is correct. Authentication may identify a caller, while authorization determines whether that caller can perform the requested action.

## What comes back?

A response includes a status code, headers, and possibly a body. The status code gives a broad result; the body may contain requested data or a useful error description. Common status groups are `2xx` for success, `4xx` for a client-side request problem, and `5xx` for a server-side problem.

## Things that can go wrong

The server may be unreachable, respond slowly, reject the input, or return an error. Clients should handle these outcomes deliberately, set suitable timeouts, and avoid blindly repeating operations that may have already succeeded. See [HTTP](../04-internet/http.md).
