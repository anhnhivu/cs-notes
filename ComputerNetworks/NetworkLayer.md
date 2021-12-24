# Network Layer: Data Plane
- local, per-router function
- determines how datagram arriving on router input port is forwarded to router output port
- forwarding function: getting through single interchange

Destination-based forwarding -> table
 - if ranges don't divide up so nicely, use 
 - Longest Prefix Matching
 - often performed using ternary content addressable memories TCAMs
 
Switching Fabrics: three types: memory, bus, crossbar.

Scheduling Algorithms

IP Addressing
- subnet part - high order bits
- host part - low order bits
- classless inter domain routing: CIDR
  - `a.b.c.d/x` 200.23.16.0/23
  - how does a host get IP address: hardcoded by system admin OR DHCP 

DHCP overview: discover, offer, request, ack

NAT (network address translation)

IPv6
- fixed length 40 byte header
- no fragmentation allowed
- no checksum


# Network Layer: Control Plane 
- network-wide logic
- between routers and from source host to destination host
- traditional routing algorithms: implemented in routers
- software-defined netowrking (SDN): implemeneted in (remote) servers -> read more

A Link-State Routing Algorithm
- Dijkstra's algorithm

Distance Vector Algorithm
- Bellman-Ford equation (dynamic programming)
- ` dx(y) = min { c(x,v) + dv(y } `

Internet Approach to Scalable Routing
- autonomous systems (AS) = domains
- intra-AS routing 
  - also known as interior gateway protocol IGP
  - most common protocols: RIP, OSPF, IGRP
  - OSPF: use link-state algorithm, topology map at each node
    - IS - IS routing: nearly identical to OSPF
    - all OSPF messages are authenticated
    - multiple same-cost paths allowed
- inter-AS routing
  - BGP border gateway protocol
  
Logical Centralized Control Plane

Reference: http://gaia.cs.umass.edu/kurose_ross/index.php 
