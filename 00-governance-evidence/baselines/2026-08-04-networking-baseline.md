# Networking Baseline — 2026-08-04

## Purpose

Assess my current ability to retrieve and explain previously studied networking fundamentals without consulting notes.

## Conditions

- No notes used during the initial attempt.
- No Internet searches used during the initial attempt.
- Corrections were performed only after completing the diagnostic.
- This baseline represents current retrieval ability, not professional competence.

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

- Rebuild the relationship between IP addressing, subnet masks, local and remote destinations, ARP, switches, default gateways, and routers.
- Practise `/24`, `/25`, and `/26` subnet calculations.
- Validate the concepts in a small Cisco Packet Tracer laboratory with one controlled configuration failure.

## Limitations

This baseline measures unaided recall at a specific point in time. It does not demonstrate production-level networking competence.

---

# Recovery Session — 2026-08-09

## Conditions

- Retrieval attempt completed without consulting notes.
- Answers were evaluated only after the retrieval attempt.
- Follow-up retrieval was used to verify concepts that initially required correction.
- Original baseline results from 2026-08-04 remain unchanged.
- `Recovered` means the concept could be retrieved again; it does not yet mean long-term retention, reproducibility, or professional competence.

## Retrieval Results

| Topic | Recovery Status | Observation | Next Action |
|---|---|---|---|
| IP addressing | Recovered | Correctly described an IP address as a logical numerical address associated with a network interface. | Reinforce its Layer 3 role through practical use. |
| Subnet masks | Recovered | Correctly explained that a subnet mask identifies the network and host portions of an IPv4 address and supports local-versus-remote destination decisions. | Apply the concept to complete subnet calculations. |
| Local vs remote networks | Recovered | Correctly identified the source IP address, destination IP address, and subnet mask as the basis for determining whether a destination is local or remote. | Practise the decision with different addresses and prefixes. |
| Default gateway | Recovered | Correctly explained that the default gateway is used when traffic must be sent outside the local network. | Validate its role later in a routed topology. |
| ARP | Recovered | After the initial ARP/ICMP confusion was corrected, correctly retrieved that ARP resolves an IPv4 address to a MAC address for local Layer 2 delivery using ARP Request and ARP Reply messages. Also distinguished ARP resolution from the later ICMP exchange used by `ping`. | Validate ARP behaviour and Ethernet delivery in Packet Tracer. |
| Switches and routers | Recovered | Correctly described a switch as forwarding Ethernet frames using MAC information and a router as forwarding IP packets between different networks using routing information. | Refine MAC-table learning and routing-table concepts through practice. |
| ICMP and ping | Recovered | After clarification, correctly distinguished ICMP from ARP and explained that `ping` uses ICMP Echo Request and Echo Reply messages to test IP reachability. | Validate ICMP Echo Request and Echo Reply in Packet Tracer and reinforce the broader role of ICMP. |
| TCP and UDP | Recovered | Correctly distinguished TCP connection establishment, reliability, ordering, and retransmission mechanisms from UDP connectionless operation without built-in delivery, ordering, or retransmission guarantees. | Reinforce overhead and protocol behaviour through later packet analysis. |
| Basic subnet calculation | Not tested | No complete subnet calculation was performed during this recovery session. The original baseline status therefore remains unchanged. | Practise complete `/24`, `/25`, and `/26` subnet calculations. |

## DNS Status

DNS was not specifically retested during this recovery session.

The original baseline status remains:

- `Retained`

It should be reviewed later as part of the normal retention cycle rather than treated as a current recovery priority.

## Recovery Summary

The recovery session shows substantial improvement compared with the initial baseline from 2026-08-04.

### Recovered

- IP addressing
- Subnet masks
- Local vs remote network decisions
- Default gateway
- ARP
- Switch vs router
- ICMP and `ping`
- TCP vs UDP

### Previously Retained

- Basic DNS purpose

### Not Yet Tested

- Basic subnet calculation

## Current Priority

Complete the Cisco Packet Tracer laboratory to validate the recovered concepts through practical network behaviour.

The laboratory should verify:

- IP addressing
- Subnet masks
- Local communication
- Local-versus-remote destination logic
- ARP Request and ARP Reply
- Ethernet frame delivery
- Switch forwarding
- ICMP Echo Request and Echo Reply
- Controlled connectivity failure
- Diagnosis
- Correction
- Final validation

After the Packet Tracer laboratory, practise complete `/24`, `/25`, and `/26` subnet calculations.

## Retention Status

The concepts listed as `Recovered` are not yet considered consolidated.

The next stages are:

1. Practical validation.
2. Delayed unaided retrieval.
3. Reproduction without the original guide.
4. Variant troubleshooting.
5. Longer-term retention checks.

A concept should only be considered consolidated after it can be retrieved, applied, and troubleshot after a meaningful delay.
