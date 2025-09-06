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

Nmap Output

<img width="694" height="279" alt="445" src="https://github.com/user-attachments/assets/794bd944-a2eb-4d6b-8163-2cc03e8a2fe1" />


---


