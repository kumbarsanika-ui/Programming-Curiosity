# Internet: challenge answers

## Questions 41–50: What happens on the internet?

### 41. What happens when you type `google.com` into a browser?

The browser interprets the address, checks relevant caches, resolves the domain through DNS if needed, establishes a network connection, negotiates TLS for HTTPS, and sends an HTTP request. It receives page resources and renders them. Many of these steps may be reused or happen in parallel.

### 42. How does your computer find Google's server?

DNS provides an IP address for the domain, often through a recursive resolver and cached records. The device then sends packets toward that address through its local network and internet routers. Large services may use multiple addresses and direct users to nearby infrastructure.

### 43. What is DNS?

The Domain Name System is a distributed, hierarchical naming system. It lets clients look up records such as an IP address for a domain. Resolvers cache answers for a time, so DNS changes may not be visible everywhere immediately.

### 44. What is an IP address?

An IP address identifies a network interface for routing packets. IPv4 and IPv6 are the two main versions. An address may be temporary, shared through NAT, or belong to an intermediary; it does not necessarily identify a person.

### 45. Why do we need ports?

An IP address helps deliver data to a device or network interface; a transport-layer port helps deliver it to the right service or connection on that device. For example, web traffic commonly uses port 443 for HTTPS. Ports are part of the endpoint, not separate physical connectors.

### 46. What is HTTP?

HTTP is an application protocol for exchanging requests and responses. A request has a method, target, headers, and sometimes a body; a response has a status, headers, and sometimes a body. Browsers and APIs use it to request and deliver resources.

### 47. Why was HTTPS created?

HTTPS protects HTTP traffic with TLS. It provides encryption in transit, detects tampering, and lets the client authenticate the server using certificates. It helps protect against eavesdropping and modification on the network, but does not prove the website itself is honest or safe.

### 48. What happens when you click a button on a website?

The browser runs the page's event-handling code. Depending on the button, it may change the page locally, validate a form, or send an HTTP request to a server. The server may process data and respond; the browser then updates the interface. A click alone does not guarantee the request succeeded.

### 49. How does your request travel thousands of kilometres?

The operating system divides network data into packets and sends them over local links. Routers forward packets between networks using IP routing; physical links may include fiber, copper, radio, or undersea cables. Packets can take different routes, and transport protocols manage delivery behavior.

### 50. How does the server know where to send the response?

The network connection records endpoint information such as the client's IP address and transport port. The server sends response data back over that connection; network devices route packets toward the client. NAT, proxies, and load balancers may translate or relay the path.

## Follow the trail

Read [DNS](./dns.md), [IP addresses](./ip.md), [HTTP](./http.md), and [HTTPS](./https.md). The [Google browsing walkthrough](../10-rabbit-holes/what-happens-when-you-open-google.md) traces the steps end to end.
