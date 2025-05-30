# Task 4: Setup and Use a Firewall on Linux

## 🎯 Objective
Configure and test basic firewall rules using UFW (Uncomplicated Firewall) and `iptables` on a Linux (Parrot OS) system to allow/block specific types of traffic.

## 🛠 Tools Used
- **UFW** (Uncomplicated Firewall)
- **iptables**
- **Telnet** and **SSH**
- **Command-line Terminal (Parrot OS)**

---

## ✅ What I Did

### 🔒 Firewall Status Check
Checked the current status and default rules:
```bash
sudo ufw status verbose
⛔ Blocked Telnet (Port 23)
sudo ufw deny 23
**Tested using:**
telnet localhost 23
##Output: Connection refused
✅ Allowed SSH (Port 22)
sudo ufw allow 22
🔄 Restored Rules (Deleted Telnet Block)
sudo ufw delete deny 23
⚙️ Using iptables to Block ICMP (Ping)
sudo iptables -A INPUT -p icmp -j DROP
Then tested using:
ping 192.168.1.3
Result: Request timed out
📸 Screenshots
Included screenshots:

UFW rules in terminal

telnet connection test

iptables command and ping test

SSH session
