# 🔍 Nmap + Wireshark Lab

This lab demonstrates how to use **Nmap** to scan a Windows machine from Kali Linux, and how to confirm the results by analyzing packets in **Wireshark**.  
We explore three common port states: **Open**, **Closed**, and **Filtered**.

---

## ⚙️ Lab Setup
- **Kali Linux (Attacker):** 192.168.20.11  
- **Windows VM (Target):** 192.168.20.10  
- **Network Mode:** Bridged (both machines on same subnet)  
- **Tools Used:**  
  - Nmap  
  - Wireshark  

## 1️⃣ Open Port (Example: TCP 445)

### Nmap Command

nmap -p 445 192.168.20.10

**Nmap Output**

<img width="750" height="578" alt="445 port" src="https://github.com/user-attachments/assets/faad18d8-cd56-4c83-864d-18455c56a8ac" />



**Wireshark Capture**

<img width="982" height="824" alt="wireshark capture" src="https://github.com/user-attachments/assets/fab62b28-79ad-4fd3-bd38-9aa12ab4dfd1" />



---


