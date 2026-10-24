# What happens when you open Google?

Opening a website looks like one action, but a browser coordinates many systems. The exact path depends on caches, browser settings, network conditions, and the services involved. This is a simplified tour of opening a site such as Google.

## 1. The browser prepares the request

The browser parses the address, checks whether it can reuse cached information, and determines which hostname it needs to contact. It may also apply browser policies, extensions, or stored preferences.

## 2. DNS finds an address

If the address is not already cached, the device asks a DNS resolver to look up the hostname. The resolver returns an IP address or another DNS result. See [DNS](../04-internet/dns.md).

## 3. A secure connection is established

The browser connects to a server at the resolved address. For HTTPS, the browser and server negotiate a TLS connection and the browser checks the server's certificate for the hostname. See [IP addresses](../04-internet/ip.md) and [HTTPS](../04-internet/https.md).

## 4. The browser sends an HTTP request

The request includes a method, headers, and possibly cookies or other state. The server may pass the request through network infrastructure, application services, and data stores before producing a response. See [HTTP](../04-internet/http.md).

## 5. The page is rendered

The response may contain HTML, CSS, JavaScript, images, and other resources. The browser interprets these, may make additional requests, and draws the page. JavaScript can update parts of the page after it first appears.

This does not mean every website uses the same architecture or contacts only one server. Large services may use caching and many distributed systems. The browser hides much of that complexity so users can focus on the page.
