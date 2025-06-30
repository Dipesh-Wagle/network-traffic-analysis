# 📸 Screenshots – Network Traffic Analysis

This folder contains terminal and Wireshark screenshots captured during the execution of **Project 2: Network Traffic Analysis using Zeek and Wireshark**.

These screenshots provide visual evidence of:
- 🧪 Simulated traffic (ping, curl, dig, nmap)
- 🧠 Zeek running in monitoring mode on `eth0`
- 🛠 Live packet capture in Wireshark using filters like:
  - `dns`
  - `http`
  - `tcp.port == 4444`

---

## 🗂 Screenshot Index

| Filename                      | Description                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| `Screenshot_1.jpg`            | Log directory listing: Zeek-generated .log files overview                 |
| `Screenshot_2.jpg`            | Top field frequency analysis from dns.log using awk and sort              |
| `Screenshot_3.jpg`            | Top source IP addresses from conn.log using awk field extraction          |
| `Screenshot_4.jpg`            | Top destination IP addresses from conn.log using awk field analysis       |
| `Screenshot_5.jpg`            | Zeek interface running: Listening on eth0                                 |
| `Screenshot_6.jpg`            | Simulated traffic: ICMP ping and curl HTTP request with redirection       |
| `Screenshot_7.jpg`            | DNS resolution using dig and Nmap scan on 1.1.1.1 revealing open ports    |
| `Screenshot_8.jpg`            | Wireshark capture showing DNS traffic with filter applied                 |
| `Screenshot_9.jpg`            | Wireshark capture showing TCP SYN packets on port 4444                    |
| `Screenshot_10.jpg`           | Wireshark capture showing HTTP GET, 301 redirect, and 200 OK responses    |

---

## 📚 Reference
For full analysis, see the [main project report](../Network_Traffic_Analysis-Report.pdf).
