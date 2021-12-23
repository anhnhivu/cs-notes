# Wireless and Mobile Networks

### Elements
- 1. wireless hosts
- 2. base station: cell towers, 802.11 access points
- 3. wireless link
- 4. infrastructure mode
- 5. ad hoc mode: no base stations
  - nodes can only transmit to other nodes within link coverage
  - nodes organize themselves into a network: route among themselves

### Wireless Network Taxonomy
- single hop + infrastructure: wifi, cellular
- single hop + no infrastructure: bluetooth, ad hoc nets 
- multiple hops: mesh net (infrastructure), manet/ vanet (no infrastructure).


### Wireless Link Characteristics
- decreses signal strength -> radio 
- interference from other sources -> standardized wireless network frequencies (2.4 GHz) shared by other devices
- multipath propagation
- SNR: signal-to-noise ratio, larger SNR -> easier to extract signal from noise -> good
- SNR vs BER (bit error rate) tradeoffs
  - given physical layer: increase power -> increase SNR -> decrease BER
  - given SNR: choose physical layer that meets BER requirement, giving the highest throughput 
- hidden terminal problem
- signal attenuation

### CDMA (code division multiple access)
- all users share the same frequency, but each user has own "chipping sequence" to encode data
- allow multiple users to coexist and transmit simultaneously with minimal interference
- encode signal = original data X chipping sequence
- decoding = inner product of encoded signal and chipping sequence

-- Read more -- 


