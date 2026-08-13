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

## Limitations

This baseline measures unaided recall at a specific point in time. It does not demonstrate production-level networking competence.

---

# Recovery Session — 2026-08-09

## Conditions

- Retrieval was attempted without consulting notes.
- Corrections were reviewed only after the initial answers.
- Recovered concepts remain subject to delayed retrieval and reproduction.
- Original baseline results remain unchanged.

## Retrieval Results

| Topic | Status | Evidence | Next Action |
|---|---|---|---|
| IP addressing | Recovered | Correctly explained the purpose of an IP address and its role in identifying network interfaces at Layer 3. | Reinforce through delayed retrieval. |
| Subnet masks | Recovered | Correctly explained that the subnet mask identifies network and host portions and is used to determine whether a destination is local or remote. | Apply to `/24`, `/25`, and `/26` calculations. |
| Local vs remote networks | Recovered | Correctly explained that a host uses the destination IP address and subnet mask to determine whether direct local delivery or a gateway is required. | Reinforce with different prefixes and routed networks. |
| Default gateway | Recovered | Correctly explained that remote traffic requires a valid next hop through a default gateway. | Validate with a routed Packet Tracer topology. |
| ARP | Recovered | Correctly distinguished ARP from DHCP and ICMP and explained IPv4-to-MAC resolution for Layer 2 delivery. | Reinforce gateway ARP behaviour in a routed topology. |
| Switches and routers | Recovered | Correctly distinguished Layer 2 frame forwarding by switches from Layer 3 packet forwarding between networks by routers. | Validate router operation practically. |
| ICMP and ping | Recovered | Correctly explained that `ping` uses ICMP Echo Request and Echo Reply to test IP reachability. | Review the limitations of `ping`. |
| TCP and UDP | Recovered | Correctly distinguished TCP reliability, ordering, connection establishment, and retransmission from UDP connectionless delivery without those built-in guarantees. | Reinforce through later packet analysis. |
| Basic subnet calculation | Not tested | Complete subnet calculations were not performed. | Practise `/24`, `/25`, and `/26`. |

## DNS Status

DNS was not retested. Its original status remains `Retained`.

---

# Packet Tracer Validation — 2026-08-09 to 2026-08-10

## Topology

PC1 → Switch → PC2

The laboratory used two hosts connected through a Layer 2 switch with `/24` IPv4 addressing.

## Successful Test

Both hosts were initially configured in the same IPv4 network.

The test validated:

- Local-versus-remote network determination using IPv4 addressing and subnet masks.
- ARP Request and ARP Reply for local IPv4-to-MAC resolution.
- Layer 2 forwarding through the switch.
- ICMP Echo Request and Echo Reply using `ping`.

## Controlled Failure

PC2 was moved to a different `/24` network while PC1 remained in its original network.

No router or default gateway was configured.

PC1 identified PC2 as a remote destination because the destination IP address did not belong to its local network according to the subnet mask.

Reaching PC2 would therefore require a valid next hop through a default gateway. The host would need to resolve the gateway's MAC address using ARP before sending the Ethernet frame to it.

Because no gateway was configured and no router existed in the topology, there was no valid next hop and communication failed.

## Diagnosis

**Root cause:** the hosts were placed in different IPv4 networks without a Layer 3 device capable of routing traffic between them.

Local communication:

PC1 determines that PC2 is local  
→ ARP resolves PC2's IPv4 address to its MAC address  
→ PC1 sends the Ethernet frame toward PC2  
→ The switch forwards the frame  
→ Communication proceeds

Remote communication:

PC1 determines that PC2 is remote  
→ A default gateway is required as the next hop  
→ ARP would resolve the gateway's IPv4 address to its MAC address  
→ The Ethernet frame would be sent to the router  
→ The router would forward the IP packet toward PC2's network

The remote path could not proceed because the topology had no configured gateway or router.

## Validation Results

| Capability | Status |
|---|---|
| IPv4 addressing | Practically validated |
| Subnet-mask application | Practically validated |
| Local vs remote determination | Practically validated |
| ARP for local delivery | Practically validated |
| Layer 2 switch forwarding | Practically validated |
| ICMP and `ping` | Practically validated |
| Default gateway | Conceptually recovered; practical validation pending |
| Router operation | Practical validation pending |
| TCP vs UDP | Not tested in this laboratory |
| Basic subnet calculation | Not tested in this laboratory |

## Current Priority

1. Practise complete `/24`, `/25`, and `/26` subnet calculations.
2. Perform delayed unaided retrieval of the recovered networking concepts.
3. Build a routed topology to validate default-gateway and router behaviour.
4. Reproduce the Packet Tracer laboratory without the original guide.

## Retention Status

Recovered and practically validated concepts are not yet considered consolidated.

Consolidation requires successful delayed retrieval, independent reproduction, and troubleshooting of a modified scenario.

---

# Delayed Retrieval and Subnetting Practice — 2026-08-13

## Conditions

- Retrieval was performed without consulting notes or study material.
- The session took place approximately four days after the recovery session and three days after completion of the Packet Tracer laboratory.
- Answers were evaluated according to technical meaning and understanding rather than exact memorization of previous wording.
- Corrections were reviewed only after completing the unaided attempt.
- Original baseline, recovery-session, and Packet Tracer results remain unchanged.

## Retrieval Results

| Topic | Status | Evidence | Next Action |
|---|---|---|---|
| IP addressing | Delayed retrieval successful | Recalled that IP provides logical addressing and supports packet delivery across local and remote networks. | Reinforce the distinction between the IP protocol and an IP address during later retrieval. |
| Subnet masks | Delayed retrieval successful | Correctly recalled that the subnet mask identifies the network and host portions of an IPv4 address. | Continue applying subnet masks through subnet calculations. |
| Local vs remote networks | Delayed retrieval successful | Correctly recalled that devices in the same local network can communicate without a router and that communication with a remote network requires Layer 3 forwarding. | Reinforce with different prefixes and routed networks. |
| Default gateway | Delayed retrieval successful | Correctly recalled that the default gateway is the router interface used by a host to reach remote networks. | Validate with a routed Packet Tracer topology. |
| ARP | Delayed retrieval successful | Correctly recalled that ARP resolves an IPv4 address to a MAC address. | Reinforce ARP behaviour when the next hop is the default gateway. |
| Basic subnet calculation | Practised — partial | Correctly identified subnet masks, network addresses, usable address ranges, and broadcast addresses for `/24`, `/25`, and `/26`. Errors remained in usable-host counts and some requested fields were omitted. | Reinforce usable-host calculations and repeat mixed `/24`, `/25`, and `/26` exercises without guidance. |

## Concepts Not Retested

The following concepts were not independently retested during this session and retain their previous status:

- Switches and routers — `Recovered`
- ICMP and `ping` — `Recovered`
- TCP and UDP — `Recovered`
- DNS — `Retained`

## Subnetting Practice Results

| Exercise | Network | Mask | First Usable | Last Usable | Broadcast | Usable Hosts | Result |
|---|---|---|---|---|---|---:|---|
| A — `192.168.10.0/24` | `192.168.10.0` | `255.255.255.0` | `192.168.10.1` | Omitted | `192.168.10.255` | 254 | Correct except for one omitted field |
| B — `192.168.10.0/25` | `192.168.10.0` | `255.255.255.128` | `192.168.10.1` | `192.168.10.126` | `192.168.10.127` | 127 | Host count incorrect; correct value is 126 |
| C — `192.168.10.128/25` | `192.168.10.128` | `255.255.255.128` | `192.168.10.129` | `192.168.10.254` | `192.168.10.255` | 127 | Host count incorrect; correct value is 126 |
| D — `192.168.10.64/26` | `192.168.10.64` | `255.255.255.192` | `192.168.10.65` | `192.168.10.126` | `192.168.10.127` | Omitted | Correct addressing; correct host count is 62 |
| E — `192.168.10.192/26` | `192.168.10.192` | `255.255.255.192` | `192.168.10.193` | `192.168.10.254` | `192.168.10.255` | Omitted | Correct addressing; correct host count is 62 |

## Observed Gap

The main subnetting gap is currently the calculation of usable host addresses rather than identification of subnet boundaries.

For the prefixes tested:

| Prefix | Total Addresses | Usable Hosts |
|---|---:|---:|
| `/24` | 256 | 254 |
| `/25` | 128 | 126 |
| `/26` | 64 | 62 |

General rule:

```text
Host bits = 32 - prefix length
Total addresses = 2^(host bits)
Usable hosts = Total addresses - 2
```

## Current Priority

1. Reinforce the distinction between total addresses and usable host addresses.
2. Repeat mixed `/24`, `/25`, and `/26` calculations without guidance.
3. Provide all six fields consistently:
   - Network address
   - Subnet mask
   - First usable host
   - Last usable host
   - Broadcast address
   - Usable host count
4. Build a routed Packet Tracer topology to validate default-gateway and router behaviour.
5. Introduce a controlled gateway or routing failure and diagnose it.
6. Reproduce the networking laboratory without the original guide.

## Retention Status

The concepts retested on 2026-08-13 remained accessible approximately four days after the 2026-08-09 recovery session.

This provides evidence of delayed retention but does not yet qualify the competencies as consolidated.

Current status:

```text
Networking fundamentals: Recovered
Subnetting: Practised — partial
Routed practical validation: Pending
Independent reproduction: Pending
Consolidation: Pending
```

Successful retrieval does not require reproducing previous documentation word for word.

The objective is to reconstruct the technical model accurately, explain it independently, and apply it to practical networking problems.
