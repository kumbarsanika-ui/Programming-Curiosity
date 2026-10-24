# DNS

The Domain Name System (DNS) helps computers find network addresses associated with names. People can remember a name such as `example.com` more easily than a numeric IP address.

## Looking up a name

When an application needs an address for a domain, it asks a DNS resolver. The resolver may already have a recent answer cached. Otherwise, it can query other DNS servers to find information for that domain and return a result.

DNS records can hold different kinds of information. An `A` record maps a name to an IPv4 address; an `AAAA` record maps it to an IPv6 address. Other records support mail delivery and additional DNS behavior.

## Caching and changes

Resolvers and devices cache answers for a limited time, specified in part by a record's time to live (TTL). Caching makes repeated lookups faster and reduces traffic, but it means a changed record may take time to be seen everywhere.

## DNS is not the whole connection

DNS finds an address; it does not by itself create a secure web connection or prove that a website is trustworthy. After a lookup, the device uses network protocols to contact the destination. See [IP addresses](./ip.md), [HTTP](./http.md), and [HTTPS](./https.md).
