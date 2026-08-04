# Networking Baseline — 2026-08-04

## Purpose

Assess my current ability to retrieve and explain previously studied networking fundamentals without consulting notes.

## Conditions

- No notes used during the initial attempt
- No Internet searches used during the initial attempt
- Corrections were performed only after completing the diagnostic
- This baseline represents current retrieval ability, not professional competence

## Results

| Topic | Status | Observed Gap | Next Action |
|---|---|---|---|
| IP addressing | Forgotten | Confused an IP address with the IP protocol and placed IP at Layer 2 instead of the network layer. | Review the purpose of IP addresses and their position in the OSI and TCP/IP models. |
| Subnet masks | Forgotten | Confused subnet masks with address hiding, NAT, and network division. | Review how a subnet mask separates the network and host portions of an IPv4 address. |
| Default gateway | Forgotten | Confused the default gateway with WLAN connectivity and public/private addressing. | Review how a host sends traffic to destinations outside its local network. |
| Switches and routers | Weak | Partially remembered that routers connect networks, but could not accurately explain switch forwarding or router operation. | Compare Layer 2 switching using MAC addresses with Layer 3 routing using IP addresses. |
| ARP | Forgotten | Confused address resolution with automatic IP address assignment. | Review how ARP maps local IPv4 addresses to MAC addresses and distinguish it from DHCP. |
| DNS | Retained | Remembered that DNS relates domain names to IP addresses, although the explanation lacked precision. | Refine the definition and review the basic DNS resolution process. |
| ICMP and ping | Weak | Remembered that `ping` checks connectivity, but did not identify ICMP or the limitations of the test. | Review ICMP Echo Request and Echo Reply and distinguish reachability from service availability. |
| TCP and UDP | Weak | Partially remembered ordered delivery in TCP, but incorrectly defined UDP. | Compare connection handling, reliability, ordering, retransmission, and overhead. |
| Basic subnet calculation | Forgotten | Did not provide the network address, usable host range, broadcast address, or usable host count. | Practise complete subnet calculations for `/24`, `/25`, and `/26` networks. |

## Retained Knowledge

- Basic DNS purpose: resolving domain names to IP addresses.

## Weak Knowledge

- Difference between switches and routers.
- Basic purpose of `ping`.
- Some TCP reliability and ordering concepts.

## Forgotten Knowledge

- Purpose and network-layer role of IP addressing.
- Function of subnet masks.
- Function of the default gateway.
- Function of ARP.
- Correct definition and behaviour of UDP.
- Complete basic subnet calculations.

## Priority for the Next Session

- Rebuild the relationship between IP addressing, subnet masks, local and remote destinations, ARP, switches, default gateways, and routers; then practise `/24`, `/25`, and `/26` subnet calculations and validate the concepts in a small Cisco Packet Tracer laboratory with one controlled configuration failure.

## Limitations

This baseline measures unaided recall at a specific point in time. It does not demonstrate production-level networking competence.
