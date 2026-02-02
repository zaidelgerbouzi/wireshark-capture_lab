# 📡 Wireshark Network Traffic & Protocol Investigation

## 📝 Overview
This lab focused on capturing and analyzing live network traffic to validate the TCP/IP stack and modern security protocols. Using Wireshark, I isolated specific protocol handshakes and investigated local-link discovery mechanisms.

## 🧠 Skills Practiced
* **Packet Capturing:** Managed live traffic captures and exported packets for offline analysis.
* **Advanced Filtering:** Used display filters (e.g., `tcp.port == 80`, `icmpv6`) to isolate conversations.
* **Protocol Analysis:** Evaluated ICMP, DNS, and TCP handshakes to verify network health.
* **Troubleshooting:** Identified clear-text HTTP signals within modern, forced HTTPS-only environments.

---

## 📸 Lab Evidence

#### A. TCP Port 80 Handshake (Layer 4)
> **Observation:** Captured the SYN → SYN-ACK → ACK sequence. I successfully isolated a clear-text HTTP/1.1 GET request to `connecttest.txt`.
![TCP Handshake](./Screenshots/tcp-port80-handshake.png)

#### B. Deep Packet Inspection (TCP Header)
> **Observation:** Analyzed the TCP header to verify Source/Destination ports and Sequence numbering for a reliable transport connection.
![TCP Header](./Screenshots/tcp-header-inspection.png)

#### C. DNS Resolution (UDP Port 53)
> **Observation:** Monitored the name resolution lifecycle via `nslookup`, showing the Standard Query and Server Response.
![DNS Query](./Screenshots/dns-query-analysis.png)

#### D. IPv6 Neighbor Discovery (ICMPv6)
> **Observation:** Captured ICMPv6 Neighbor Solicitation/Advertisement messages, demonstrating how IPv6 manages local discovery without ARP.
![ICMPv6](./Screenshots/icmpv6-neighbor-discovery.png)

---

#### 🛡 Notes on Modern Protocol Behavior
While most web traffic is now encrypted via TLS/HTTPS (Port 443), this lab successfully targeted Port 80 to observe raw protocol headers. This demonstrates an understanding of the differences between secure and unencrypted traffic—essential for network troubleshooting and security analysis.
