<img align="left" src="https://raw.githubusercontent.com/0x4D31/fatt/master/docs/fatt.png" width="150px">

fingerprint all the things!

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

> More info about the fingerprinting methods, sample use-cases and research results will be added to the repo soon. Stay tuned!

A script for extracting network metadata and fingerprints such as [JA3](https://github.com/salesforce/ja3) and [HASSH](https://github.com/salesforce/hassh) from packet capture files (pcap) or live network traffic. The main use-case is for monitoring honeypots, but you can also use it for other use cases such as network forensic analysis. fatt works on Linux, macOS and Windows.

Note that fatt uses pyshark (a python wrapper for tshark) and therefore the performance is not great! But that's not a big issue as obviously this is not a tool you use in production. You can use other network analysis tools such as [Bro/Zeek](https://github.com/bro/bro), [Suricata](https://github.com/OISF/suricata) or [Netcap](https://github.com/dreadl0ck/netcap) for more serious use cases. [Joy](https://github.com/cisco/joy) is another great tool you can use for capturing and analyzing network flow data.

Other than that, I'm working on a go based version of fatt which is faster, and you can use its libraries in your gopacket based tools such as packetbeat. I released the initial version of its gQUIC library ([QUICk](https://github.com/0x4D31/quick)).


### Features

- Protocol support: SSL/TLS, SSH, RDP, HTTP, gQUIC.
    - To be added soon: IETF QUIC, MySQL, MSSQL, etc.
- Fingerprinting
    - JA3: TLS client/server fingerprint
    - HASSH: SSH client/server fingerprint
    - RDFP: my experimental RDP fingerprint for standard RDP security protocol (note that other RDP security modes use TLS and can be fingerprinted with JA3)
    - HTTP header fingerprint
    - gQUIC/iQUIC fingerprint will be added soon 
- JSON output
