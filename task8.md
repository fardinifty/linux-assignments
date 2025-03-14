## **Firewall Configuration Report**

### **1. Introduction**
This report outlines the firewall rules implemented to protect the server. The rules ensure secure access to essential services (SSH, HTTP, and HTTPS), log blocked connections, and mitigate common attacks such as SYN floods.

---

### **2. Firewall Rules**
Below are the firewall rules defined, with explanations for each:

#### **Allow SSH (Port 22)**
```bash
sudo ufw allow ssh
```
> **Reason:** This rule allows remote administration via SSH.

#### **Allow HTTP and HTTPS (Ports 80 & 443)**
```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```
> **Reason:** These rules allow web traffic for websites hosted on the server.

#### **Deny All Other Incoming Connections**
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```
> **Reason:** Denying all other connections ensures only the defined services are accessible.

#### **Enable Logging**
```bash
sudo ufw logging on
```
> **Reason:** Logs provide visibility into blocked or suspicious activities.

#### **SYN Flood Protection**
Added in `/etc/ufw/before.rules` before `COMMIT`:
```bash
# SYN flood protection
-A ufw-before-input -p tcp --syn -m limit --limit 10/s --limit-burst 20 -j ACCEPT
```
> **Reason:** Limits SYN packets to reduce the risk of SYN flood attacks, which can overwhelm the server.

#### **Additional Attack Protection Rules**
Added in `/etc/ufw/before.rules` before `COMMIT`:

**Drop NULL Packets:**
```bash
-A ufw-before-input -p tcp --tcp-flags ALL NONE -j DROP
```
> **Reason:** NULL packets are often used in reconnaissance scans.

**Drop Xmas Packets:**
```bash
-A ufw-before-input -p tcp --tcp-flags ALL ALL -j DROP
```
> **Reason:** Xmas packets are often used to bypass firewalls.

**Drop FIN Scan Attempts:**
```bash
-A ufw-before-input -p tcp --tcp-flags ALL FIN -j DROP
```
> **Reason:** FIN scans attempt to identify open ports through stealth methods.

---

### **3. Testing and Verification**
- Used `nmap` to confirm open ports: **22**, **80**, and **443**.
- Verified logs in `/var/log/ufw.log` for blocked traffic and suspicious patterns.
- Simulated SYN flood attack with `hping3` to ensure the firewall effectively mitigated the attack.

---

### **4. Conclusion**
This firewall configuration successfully secures the server by:
- Allowing only essential services.
- Blocking unauthorized access.
- Protecting against SYN flood and other common attacks.
- Providing detailed logging for security monitoring.

