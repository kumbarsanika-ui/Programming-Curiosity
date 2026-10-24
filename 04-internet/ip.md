# IP addresses

An Internet Protocol (IP) address identifies a network interface so data can be routed toward it. Devices use IP addresses to send packets across networks, much as a postal system uses destination information to forward mail.

## IPv4 and IPv6

IPv4 addresses are commonly written as four numbers separated by dots, for example `192.0.2.10`. IPv6 uses a longer hexadecimal format, for example `2001:db8::10`. IPv6 provides a much larger address space.

Addresses may be public, reachable across the internet subject to network rules, or private, used within a local network. A router often lets several devices share one public IPv4 address using network address translation (NAT).

## Packets and routing

Network data is split into packets. Each packet carries addressing information, and routers forward it between networks. Different packets in a communication may take different routes. Higher-level protocols handle details such as putting data in order or retrying after loss.

An IP address is not necessarily a permanent identifier for a person or device. Addresses can change, be shared, or represent an intermediary such as a VPN or proxy.

DNS connects memorable domain names to addresses; IP carries packets toward those addresses. See [DNS](./dns.md).
