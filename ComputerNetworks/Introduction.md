# Introduction

Reference: [Professor Jim Kurose](https://gaia.cs.umass.edu/kurose_ross/ppt.php)

## Topics
1. Network Architecture, OSI, and TCP/IP reference models.
2. Network technologies: LAN (Ethernet, wireless, bluetooth)
3. Routing and internetworking, Internet adddressing routing.
4. Internet transport protocol: UDP and TCP
5. Network programming interface
6. Application layer protocols and applications: DNS, email, WWW.

## Introduction
**"nuts and bolts" view**: network of networks

Protocols: TCP, IP, HTTP, Skype, 802.11

Internet standards
- RFC: Request For Comments
- IETF: Internet Engineering Task Force

**a service view**

- infrastructure that provides services to applications:
    - Web, VoIP, email, games, e- commerce, social nets, ...
- provides programming interface to apps
    - provides service options

### Network Edge
- end systems
  - hosts: clients and servers
  - serveres often in data centers

**Access network**
- digital subscriber line (DSL)
- cable network
  - frequency division multiplexing: differenct channels -> different frequency bands
  - shared 
  - HFC: hybrid fiber coax
- home network
- Ethernet 
- wireless LANs: WiFi 802.11 b/g/n
- wide-area wireless access: cellular, 3G, 4G, LTE

`transmission rate R = link capacity = link bandwidth`

`packet transmission delay = time needed to transmit L-bit packet into link = L(bits) / R (bits/sec)`

**Physical Media**

- Coaxial Cable: two concentric copper conductors, bidirectional, broadband: HFC
- Fiber Optic Cable: glass fiber carrying light pulse, high-speed, low error rate, immune to electromagnetic noise
- Radio: signal carried in electromagnetic spectrum, bidirectional, propagation environment effects: reflection, obstruction by objects, interference
   - terrestrial microwave
   - LAN (WiFi)
   - wide-area (cellular)
   - satellite

### Network Core
- interconnected routers
**packet switching** 
- store and forward: entire packet must arrive before transmitted to the next link
  - `end-end delay = 2L/R`
- queueing delay, loss -> excessice congestion possible
- two key functions: routing and forwarding
- allows MORE users to use the network
- with 35 users, probability > 10 active at the same time is less than .0004
- great for bursty data, simpler, no call setup, resource sharing
**circuit switching** 
- dedicated resource: no sharinf
- commonly used in traditional telephone networks
- frequency vs time division


## Calculating delay, loss, throughput

``` d_nodal = d_proc + d_queue + d_trans + d_prop```

- `d_proc`: nodal processing: check bit errors, determine output link: < msec
- `d_queue`: queueing delay: time waiting at output link, depends on congestion level of router
  - `La/R = 0`: delay small, `La/R -> 1` large (`a`: average packet arrival rate)
- `d_trans`: transmission delay: `L(bits) / R (bps)` -> service at toll booth
- `d_props`: propagation delay: `d (length) /s (speed)` -> propagate through the link

Throughput: 
- rate (bits/time unit): instantaneous, average
- bottleneck link 

## Internet Protocol Stack
```
 - - - - - - -
| application | supporting network applications
 - - - - - - -
| transport   | process-process data transfer
 - - - - - - - 
| network     | routing from source to destination
 - - - - - - - 
| link        | transfer between neighboring network elements
 - - - - - - - 
| physical    | bits on the wire
 - - - - - - - 
 ```
 
 ISO/OSI Reference Model: presentation + session layer between application and transport layers
 
 
## Network Security
- malware can get in host from: virus, worm (passively receiving)
- infected host can be enrolled in botnet, used for spam DDoS attacks
- Denial of Service (DoS) 
- packet sniffing
- IP spoofing


