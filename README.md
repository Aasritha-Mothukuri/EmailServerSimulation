# 📧 EmailServerSimulation
Simulation of a local email server using Cisco Packet Tracer, demonstrating **SMTP** and **POP3** protocols for sending and receiving emails between multiple PCs.

---

## 📝 Project Overview
This project demonstrates the design and implementation of a **functional email communication system** using Cisco Packet Tracer.  
Multiple PCs communicate through a **dedicated email server**, showcasing:

- **SMTP** (Simple Mail Transfer Protocol) → Sending emails  
- **POP3** (Post Office Protocol) → Receiving emails  

---

## 🎯 Objectives
- 🖥️ Design and implement a local email server simulation.  
- 🌐 Configure communication between multiple PCs and the mail server.  
- 📤 Demonstrate SMTP and POP3 protocols in action.  
- ✅ Verify successful email transmission between users.  

---

## 🖧 Network Topology & Devices
| Device Type | Device Name | Icon | Description |
|-------------|------------|------|-------------|
| Router      | 2911       | 🛡️  | Connects networks 10.0.0.x and 192.168.1.x |
| Switch      | 2960       | 🔀   | Central connection for all PCs and server |
| PC          | PC0–PC3    | 🖥️   | End devices for sending and receiving emails |
| Server      | Email Server | 🗄️ | Handles SMTP and POP3 services |

---

## 🌐 IP Addressing Scheme

| Device | IP Address     | Subnet Mask     | Default Gateway | Icon |
|--------|----------------|----------------|----------------|------|
| PC0    | 10.0.0.2       | 255.0.0.0      | 10.0.0.1       | 🖥️ |
| PC1    | 10.0.0.3       | 255.0.0.0      | 10.0.0.1       | 🖥️ |
| PC2    | 10.0.0.4       | 255.0.0.0      | 10.0.0.1       | 🖥️ |
| PC3    | 10.0.0.5       | 255.0.0.0      | 10.0.0.1       | 🖥️ |
| Server | 192.168.1.2    | 255.255.255.0  | 192.168.1.1    | 🗄️ |

---

## 🖧 Network Topology Diagram


    
    🖥️ PC0      🖥️ PC1
       \          /
        🔀 Switch
       /          \
    🖥️ PC2      🖥️ PC3
           |
         🛡️ Router 2911
           |
         🗄️ Server


- 🖥️ → PCs  
- 🗄️ → Server  
- 🔀 → Switch  
- 🛡️ → Router

---

## 🛠️ Step-by-Step Procedure

### 1️⃣ Device Setup
- Added 4 PCs, 1 switch, 1 router, and 1 server.  
- Connected devices using **straight-through Ethernet cables**.  

### 2️⃣ PC Configuration
- Open each PC → Desktop → IP Configuration  
- Assign IP addresses, subnet masks, and default gateways as per the table above.  

### 3️⃣ Router Configuration
- Router → Config Tab → Interfaces  
  - **Gig0/0** → IP: `10.0.0.1` / Subnet: `255.0.0.0`  
  - **Gig0/1** → IP: `192.168.1.1` / Subnet: `255.255.255.0`  

### 4️⃣ Server Configuration
- Server → Desktop → IP Configuration → IP: `192.168.1.2` / Subnet: `255.255.255.0` / Gateway: `192.168.1.1`  
- Services → **Email**  
  - Domain: `gmail.com`  
  - Users: `user1`, `user2`, `user3`, `user4` (Password: `123`)  
  - Turn **ON** SMTP and POP3  

### 5️⃣ PC Email Setup
- Desktop → Email → Fill Details:  

| PC   | Email Address       | Incoming/Outgoing Server | Username | Password |
|------|------------------|------------------------|----------|----------|
| PC0  | user1@gmail.com    | 192.168.1.2           | user1    | 123      |
| PC1  | user2@gmail.com    | 192.168.1.2           | user2    | 123      |
| PC2  | user3@gmail.com    | 192.168.1.2           | user3    | 123      |
| PC3  | user4@gmail.com    | 192.168.1.2           | user4    | 123      |

---

## 📤 Protocols Used

### SMTP (Simple Mail Transfer Protocol) – Sending Emails
- **Purpose:** Sends emails from a client to a mail server or between mail servers.  
- **How it works:**  
  1. User composes an email on a PC.  
  2. PC connects to the **SMTP server** (`192.168.1.2`).  
  3. SMTP delivers the email to the recipient’s server.  
- **Port:** 25 (default), 587 (secure).  
- **Key Point:** SMTP only sends emails; it does not retrieve them.  
- **Analogy:** SMTP = **mailman delivering letters**.  

### POP3 (Post Office Protocol 3) – Receiving Emails
- **Purpose:** Retrieves and downloads emails from the mail server to the client PC.  
- **How it works:**  
  1. Email client connects to the **POP3 server**.  
  2. Downloads emails to the PC inbox.  
  3. Emails are usually deleted from the server after download (can keep a copy).  
- **Port:** 110 (default), 995 (secure).  
- **Key Point:** POP3 is download-only.  
- **Analogy:** POP3 = **collecting letters from your mailbox**.  

### 🔄 How SMTP and POP3 Work Together

PC0 (Sender) --[SMTP]--> Mail Server --[POP3]--> PC1 (Receiver)

- Step 1: SMTP sends email from sender to server  
- Step 2: POP3 retrieves email from server to recipient  

---

## ✅ Testing & Verification
1. Compose email on **PC0** → To: `user2@gmail.com`  
   - Subject: `Test Mail`  
   - Message: `Hi, how are you?`  
2. On **PC1**, click **Receive** → Email received successfully via POP3  
3. Repeat similar tests between **PC2 ↔ PC3**  
4. All emails sent and received successfully  

---

## 📊 Results
- All PCs successfully communicated through the email server.  
- Router correctly routed traffic between **10.0.0.x** and **192.168.1.x** networks.  
- Server handled **SMTP** and **POP3** without errors.  

---

## 🏁 Conclusion
- Successfully designed a local email communication system in Cisco Packet Tracer.  
- Configured IP addresses, router interfaces, and mail server correctly.  
- Implemented SMTP and POP3 protocols for email delivery.  
- Demonstrated understanding of client-server networking and email protocols.  
