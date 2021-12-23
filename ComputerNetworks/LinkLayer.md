# Link Layer

implemented in each and every host -> in adaptor (NIC) or chip

EDC = error detection and correction bits (redundancy) 

D = data protected by error checking, may include header fields

Error detection may miss some errors, but rarely -> larger EDC field -> better

Parity checking
- single bit 
- two-dimensional bit

Internet checksum -> detect flipped bits transport layer
- sender: treat segment content as 16-bit integers, checksum (1's complement sum) of 
segement contents -> sender puts checksum value into UDP checksum field
- receiver: compute checksum, check if it equals the checksum field value

Cyclic Redundancy Check
- more powerful error-detection coding
- widely used in practice (Ethernet, 802.11 WiFi, ATM) 
