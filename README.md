# 🔐 Ubuntu Linux Security Lab

A production-style, multi-layered security environment built from scratch on Ubuntu 22.04 LTS inside VirtualBox — simulating a real-world SOC infrastructure.

## 🛠️ Tools & Technologies

| Tool | Version | Purpose |
|------|---------|---------|
| Ubuntu | 22.04 LTS | Base operating system |
| iptables | 1.8.x | Firewall & packet filtering |
| Suricata | 7.x | Intrusion detection & prevention |
| WireGuard | 1.x | Encrypted VPN tunnel |
| Wazuh | 4.7 | SIEM & security monitoring |
| Prometheus | 2.54 | Metrics collection & storage |
| Grafana | Latest | Real-time monitoring dashboard |
| Node Exporter | 1.8.2 | System metrics exporter |

## 📁 Project Phases

### Phase 1 — Environment Setup
- Deployed Ubuntu 22.04 LTS on VirtualBox with bridged networking
- Enabled OpenSSH server for remote management
- Configured system updates and essential security tools

### Phase 2 — Firewall (iptables)
- Default DROP policy on INPUT and FORWARD chains
- Stateful packet inspection using conntrack
- NULL and XMAS scan protection
- SSH brute-force rate limiting (4 attempts/min)
- Persistent logging of all dropped packets

### Phase 3 — Intrusion Detection (Suricata)
- Suricata 7.x with Emerging Threats ruleset (50,000+ signatures)
- Custom detection rules for ICMP, SSH brute force, Nmap scans
- Real-time alerting via eve.json logs

### Phase 4 — VPN (WireGuard)
- Curve25519 key pairs for encrypted peer authentication
- ChaCha20-Poly1305 encrypted tunnel
- IP forwarding and NAT masquerading
- Integrated with existing iptables firewall

### Phase 5 — SIEM (Wazuh)
- Full Wazuh stack (indexer + manager + dashboard)
- Real-time threat detection and alerting
- MITRE ATT&CK framework mapping
- System integrity and vulnerability monitoring

### Phase 6 — Monitoring (Prometheus + Grafana)
- Node Exporter collecting 1000+ system metrics
- Prometheus scraping metrics every 15 seconds
- Grafana dashboard showing CPU, RAM, disk, network in real time
- Custom alert rules for high CPU, memory, and disk usage

## 📂 Repository Files

| File | Description |
|------|-------------|
| iptables-rules.txt | Exported firewall rules |
| suricata-local.rules | Custom Suricata detection rules |
| wireguard-server-template.conf | WireGuard server config template |
| prometheus.yml | Prometheus scrape config |
| node_exporter.service | Node Exporter systemd service |
| prometheus.service | Prometheus systemd service |

## ⚠️ Security Notes
- Private keys are never stored in this repository
- WireGuard config is a template only — replace key placeholders before use
- This lab is intended for educational purposes in an isolated VM environment

## 👤 Author
**Ahmed Mohsen Abd-Elmonim**
- 💼 [LinkedIn](http://linkedin.com/in/ahmedmohsenabdelmanam)
- 🐙 [GitHub](https://github.com/AAhmedMohsen)
