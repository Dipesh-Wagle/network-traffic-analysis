
# 🕵️ Network Traffic Analysis Project

## 🎯 Objective
Capture and analyze network traffic using Wireshark and Zeek to detect suspicious activity such as DNS anomalies, port scans, and HTTP-based threats.

---

## 🧰 Tools Used
- **Wireshark** – for packet capture and analysis
- **Zeek (formerly Bro)** – for real-time network traffic logging
- **Kali Linux (x86_64)** – operating environment
- **Ping, Curl, Dig, Nmap** – traffic simulation tools

---

## 🛠️ Setup Steps

### 🔹 1. Install Wireshark
```bash
sudo apt update
sudo apt install wireshark -y
sudo usermod -aG wireshark $USER
newgrp wireshark
```

### 🔹 2. Launch Wireshark
```bash
wireshark &
```
Start capturing on the correct interface (e.g., eth0 or wlan0).

---

### 🔹 3. Simulate Traffic
```bash
ping google.com
curl http://example.com
curl https://ifconfig.me
dig facebook.com
nmap -sS -T4 -Pn <target_ip>
```

---

### 🔹 4. Install and Run Zeek
```bash
sudo apt update
sudo apt install zeek -y
```

#### Run Zeek:
```bash
sudo nohup /opt/zeek/bin/zeek -i eth0 -C > /opt/zeek/zeek.out 2>&1 &
```

---

### 🔹 5. Analyze Zeek Logs
```bash
ls -la | grep .log
```

#### Example Log Queries:
- Top DNS Queries:
  ```bash
  cat dns.log | awk '{print $9}' | sort | uniq -c | sort -nr | head
  ```
- Top Talkers:
  ```bash
  cat conn.log | awk '{print $3}' | sort | uniq -c | sort -nr | head
  ```

---

### 🔹 6. Useful Wireshark Filters
- HTTP: `http`
- DNS: `dns`
- Suspicious Ports: `tcp.port == 4444 || udp.port == 53`
- ICMP Scans: `icmp.type == 8`

---

### 📊 Visual Analysis

#### 🔸 Top 10 Queried Domains
![Top Domains](network_plots/top_domains.png)

#### 🔸 Top 10 Destination Ports
![Top Ports](network_plots/top_ports.png)

#### 🔸 Top 10 HTTP User Agents
![Top User Agents](network_plots/top_user_agents.png)

---

## ✅ Status Checklist
| Task                           | Status |
|--------------------------------|--------|
| Zeek running in background     | ✅     |
| Wireshark captures traffic     | ✅     |
| Traffic simulation done        | ✅     |
| Logs captured (Zeek)           | ✅     |
| Anomalies identified           | ✅     |
| Charts Generated               | ✅     |
| Ready for report/export        | ✅     |
