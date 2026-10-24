# What is an API?

An application programming interface (API) is a defined way for one piece of software to use another. It describes what operations are available, what inputs they accept, and what results or errors callers can expect.

## Everyday analogy

Think of a restaurant menu as a limited interface: it lists what can be ordered and what information the kitchen needs. A customer does not need to know how the kitchen is organized. Similarly, a program can use an API without knowing the internal implementation behind it.

## Different kinds of APIs

A library API may let code call functions in the same program. An operating-system API provides access to services such as files. A web API lets software communicate over a network, often using HTTP and formats such as JSON.

For example, a weather application might send a request to a weather service with a location and receive a structured forecast. The service controls which operations are available and may require credentials, impose usage limits, or charge for access.

## Contracts and errors

A useful API has documented inputs, outputs, and failure cases. Callers should validate results and handle errors such as unavailable services, invalid requests, or denied access. See [Request and response](./request-response.md) and [REST APIs](./rest-api.md).
