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

Packet Sequence:

SYN → SYN/ACK → RST


✅ Interpretation: Port 445 is open and Windows is running SMB service.

---

## 2️⃣ Closed Port (Example: TCP 50000)
Nmap Command
nmap -p 50000 192.168.20.10

**Nmap output**

<img width="982" height="824" alt="port 50000" src="https://github.com/user-attachments/assets/5b7689b9-bcd6-4fb4-ae4a-1775e531f6fa " />

**Wireshark Capture**

<img width="1920" height="947" alt="50000" src="https://github.com/user-attachments/assets/4097378f-ad27-4f54-8ec1-df10ab95ff50" />

Packet Sequence:

SYN → RST/ACK


✅ Interpretation: Port 50000 is closed because Windows actively rejected the connection.

## 3️⃣ Filtered Port (Example: TCP 21)
Nmap Command
nmap -p 21 192.168.20.10

**Nmap Output**

<img width="877" height="205" alt="port 21" src="https://github.com/user-attachments/assets/5c283e3f-8a1a-4c98-aec6-7adf27015998" />

**Wireshark Capture**

<img width="1920" height="947" alt="wireshark 21" src="https://github.com/user-attachments/assets/64aaae0d-685b-42b4-a88f-93f060b76563" />

Packet Sequence:

SYN → (no reply, retransmits)


✅ Interpretation: Port 21 is filtered because Windows Firewall silently dropped the packets.


📖 **Conclusion**

Open port: Service is listening and responded with SYN/ACK.

Closed port: No service; Windows replied with RST/ACK.

Filtered port: Firewall blocked packets; no reply received.

This lab shows how Nmap results can be verified at the packet level with Wireshark, providing a deeper understanding of network scanning and port states.

---
