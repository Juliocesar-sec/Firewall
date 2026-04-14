🔥 What is a Firewall?
A firewall is a system (software or hardware) that controls network traffic, allowing or blocking connections based on security rules.
👉 It works like a “bouncer” or gatekeeper for your network:

Decides who can enter
Decides who can leave
Filters what is safe versus what is suspicious

🎯 Importance in IT and Cybersecurity
The firewall is one of the first lines of defense in any network.
Main functions:

🔐 Block unauthorized access
🌍 Control internet traffic
🛡️ Reduce the attack surface
📊 Monitor suspicious activity
🚫 Prevent exploitation of ports and services

👉 Without a firewall = your network is practically exposed.

🌐 DNS / Name Resolution (Port 53/tcp)
What is DNS?
DNS (Domain Name System) translates human-readable names into IP addresses, for example: 

```bash
oogle.com → 142.250.x.x
```
⚠️ Risks:

DNS Spoofing / Cache Poisoning
→ Attackers manipulate DNS responses to redirect victims to malicious sites.
DDoS Amplification
→ DNS servers are abused to amplify attacks against third parties.
Unauthorized Zone Transfer
→ Leakage of the entire domain structure and internal records.

🛡️ Protection with Firewall:

Allow DNS traffic only to trusted servers
Block unnecessary external queries
Monitor for anomalous DNS traffic


🖥️ REMOTE ACCESS
🔸 22/tcp – SSH (Secure)

Encrypted remote access

⚠️ Risks:

Brute-force attacks
Weak passwords
Poor key management

🛡️ Protection:

Block unrestricted external access
Use IP whitelisting
Prefer key-based authentication (instead of passwords)

🔸 23/tcp – Telnet (Insecure 🚨)

Does not use encryption

⚠️ Risks:

Credentials sent in plain text
Session hijacking

🛡️ Protection:

❌ Block completely in the firewall
Replace with SSH

🔸 5900/tcp – VNC

Graphical remote desktop access

⚠️ Risks:

Weak passwords
No encryption (in older versions)

🛡️ Protection:

Use over VPN
Restrict by IP
Enable encryption


📁 FILE SHARING
🔸 21/tcp – FTP
⚠️ Risks:

Clear-text login
Malware uploads

🛡️ Protection:

Avoid → use SFTP instead
Block public access

🔸 445/tcp – SMB (Highly Critical 🚨)
⚠️ Risks:

Ransomware (e.g., WannaCry)
Remote Code Execution (RCE)

🛡️ Protection:

❌ Never expose to the internet
Allow only on internal networks

🔸 2049/tcp – NFS
⚠️ Risks:

Unauthorized directory access
Privilege escalation

🛡️ Protection:

Restrict by IP
Configure exports properly


🗄️ DATABASES
🔸 3306 – MySQL
🔸 5432 – PostgreSQL
🔸 6379 – Redis
🔸 27017 – MongoDB
⚠️ Common Risks:

Databases exposed to the internet
Weak passwords
Lack of authentication

🛡️ Protection:

❌ Never make them public
Allow access only from internal network or VPN
Firewall should block everything by default


⚙️ SYSTEM SERVICES
🔸 111/tcp – rpcbind
⚠️ Risks:

Service enumeration
Exposure of internal information

🛡️ Protection:

Block external access
Allow only trusted hosts


📡 UDP / NETWORK DISCOVERY
🔸 1900/udp – SSDP / UPnP
⚠️ Risks:

DDoS amplification
Device exposure

🛡️ Protection:

Disable UPnP when possible
Block at the network edge

🔸 5353/udp – mDNS
⚠️ Risks:

Local information leakage
Spoofing

🛡️ Protection:

Limit to local network only
Block on public networks


🧠 IMPORTANT SUMMARY
👉 In cybersecurity, the golden rule is:
“If it doesn’t need to be open → it should be closed.”
The firewall helps you:

Reduce exposure
Control critical ports
Prevent automated attacks

🛡️ GENERAL BEST PRACTICES

🔒 Principle of least privilege
🌐 Use VPN for remote access
🚫 Block all unnecessary ports
🔑 Use strong authentication
📊 Monitor logs continuously
