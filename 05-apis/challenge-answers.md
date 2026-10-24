# APIs: challenge answers

## Questions 51–60: The invisible communication

### 51. What exactly is an API?

An API is a documented interface that lets one piece of software request operations or information from another. It defines available operations, expected inputs, results, and errors, while hiding many internal implementation details.

### 52. Why can’t two applications simply access each other’s variables?

Separate applications normally run in separate process address spaces, often on different computers. Directly sharing a variable would require shared memory, compatible representations, synchronization, and permissions. An API provides a controlled, language-independent contract for exchanging data and requesting actions.

### 53. What happens when a React application calls a Node.js or Python API?

The React code typically serializes data, sends an HTTP request over the network, and waits asynchronously. A Node.js or Python server receives it, validates it, authenticates and authorizes the caller as needed, performs application logic, and returns a response. The browser parses the result and updates the interface.

### 54. What is a request?

A request is a client's message asking a service to retrieve information or perform an operation. An HTTP request includes a method and URL, may include headers, and can contain a body. Requests can fail before they reach a server.

### 55. What is a response?

A response is the service's reply. It commonly includes a status code, headers, and a body with requested data or an error description. Clients should examine the status and validate the returned data instead of assuming every response is successful.

### 56. Why do APIs commonly use JSON?

JSON is a text format that is easy for many languages to produce and parse. It represents common values such as objects, arrays, strings, numbers, booleans, and null. It is widely supported, though it has limitations—for example, it has no native date or binary type.

### 57. What are HTTP methods?

HTTP methods describe the intended operation on a resource. Common methods include `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`. Their semantics help clients, servers, caches, and intermediaries reason consistently about requests.

### 58. Why do we have `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?

They express different intentions: `GET` retrieves; `POST` submits data or requests an operation; `PUT` replaces a resource representation; `PATCH` applies a partial change; `DELETE` removes a resource. `GET` is intended to be safe, and `PUT` and `DELETE` are generally idempotent by HTTP semantics; actual API behavior should follow its documented contract.

### 59. What happens if an API takes 10 seconds to respond?

The client remains waiting unless it times out or cancels. The interface may appear unresponsive if it does not show progress. Good clients use timeouts, loading states, and carefully chosen retries; retrying a non-idempotent operation can accidentally repeat an action.

### 60. What happens if the API server is completely down?

The request may fail to connect or time out. The client should report a useful temporary failure, preserve user input where possible, and avoid an unbounded retry loop. Operators use health checks, monitoring, logs, redundancy, and recovery procedures to restore service.

## Follow the trail

Read [what an API is](./what-is-api.md), [requests and responses](./request-response.md), and [REST APIs](./rest-api.md).
