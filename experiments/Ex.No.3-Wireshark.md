# Ex.No.3 — Wireshark Network Packet Capture and Analysis Tool

![Wireshark](https://img.shields.io/badge/Tool-Wireshark-green)
![Platform](https://img.shields.io/badge/Platform-Cross--Platform-orange)
![Type](https://img.shields.io/badge/Analysis-Network%20Analysis-blue)

**📚 Course / Lab:** Digital Forensics Lab  
**🔢 Experiment No.:** 3  
**📝 Title:** Wireshark – Network Packet Capture and Analysis Tool

---

## 📑 Table of Contents

- [Ex.No.3 — Wireshark Network Packet Capture and Analysis Tool](#exno3--wireshark-network-packet-capture-and-analysis-tool)
  - [📑 Table of Contents](#-table-of-contents)
  - [🎯 Aim](#-aim)
  - [🛠️ Requirements](#️-requirements)
  - [📝 Description](#-description)
  - [🌐 Website Used](#-website-used)
  - [📋 Procedure: Capturing Plaintext Passwords](#-procedure-capturing-plaintext-passwords)
    - [Step 1: Start Capturing Packets](#step-1-start-capturing-packets)
    - [Step 2: Generate Login Traffic](#step-2-generate-login-traffic)
    - [Step 3: Stop Capture and Filter Traffic](#step-3-stop-capture-and-filter-traffic)
    - [Step 4: Inspect the Packet to Find Credentials](#step-4-inspect-the-packet-to-find-credentials)
  - [✅ Result](#-result)
  - [📝 Notes](#-notes)

---

## 🎯 Aim
To demonstrate how to use **Wireshark** for network packet capture and analysis, specifically focusing on capturing and analyzing plaintext passwords transmitted over HTTP connections to understand network security vulnerabilities.

---

## 🛠️ Requirements

- **💻 Computer with network connectivity**
- **🔧 Wireshark** (Network Protocol Analyzer)
- **🌐 Web browser** (Chrome, Firefox, Edge, etc.)
- **📡 Active network interface** (Wi-Fi or Ethernet)
- **🎯 Test website** for demonstration purposes

---

## 📝 Description
Wireshark is a powerful **network protocol analyzer** that allows users to capture and interactively browse the traffic running on a computer network. It is widely used by network administrators, security professionals, and forensic investigators to analyze network communications, troubleshoot network issues, and identify security vulnerabilities. This experiment demonstrates how easily plaintext credentials can be intercepted when transmitted over unsecured HTTP connections.

---

## 🌐 Website Used
**🔗 Test Site:** [http://demo.testfire.net/](http://demo.testfire.net/)

⚠️ **Note:** This is a deliberately vulnerable web application designed for security testing and educational purposes.

---

## 📋 Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets

**🎯 Purpose:** Initialize Wireshark and begin network traffic capture.

**📋 Instructions:**

1. **🚀 Open Wireshark application.**

2. **📡 You will see a list of all available network interfaces:**
   - Wi-Fi adapter
   - Ethernet adapter
   - Loopback interface

3. **🔍 Select the network interface your computer is using to connect to the internet** (typically Wi-Fi or Ethernet).

<details>
<summary>🖥️ View Network Interface Selection</summary>
<br>
<p align="center">
  <img width="859" alt="Wireshark interface selection screen" src="https://github.com/user-attachments/assets/d2d2f108-c7c4-4802-ac9e-c8635263ca5c" />
</p>
</details>

4. **🦈 Click the blue shark fin icon in the top-left corner to start the capture.**
   - Wireshark will immediately begin capturing all network traffic passing through the selected interface.

<details>
<summary>📊 View Packet Capture Interface</summary>
<br>
<p align="center">
  <img width="750" alt="Wireshark packet capture in progress" src="https://github.com/user-attachments/assets/542d082e-68d0-427d-a595-e90c7a25d1c0" />
</p>
</details>

---

### Step 2: Generate Login Traffic

**🎯 Purpose:** Create network traffic containing login credentials for analysis.

**📋 Instructions:**

1. **🌐 Open a web browser and navigate to:** `http://demo.testfire.net/`

2. **👤 Enter dummy credentials for testing:**
   - **Username:** `testuser`
   - **Password:** `password123`

3. **🔐 Click the login button.**
   - The login will fail (expected behavior)
   - However, the credentials have been transmitted over the network

<details>
<summary>🔐 View Login Process</summary>
<br>
<p align="center">
  <img width="645" alt="Demo website login form with test credentials" src="https://github.com/user-attachments/assets/52371b26-88cc-4578-8535-4c50f6c7516d" />
</p>
</details>

---

### Step 3: Stop Capture and Filter Traffic

**🎯 Purpose:** Stop packet capture and isolate relevant HTTP traffic for analysis.

**📋 Instructions:**

1. **⏹️ Return to Wireshark and click the Stop button** (red square icon).

2. **🔍 Apply a display filter to find the login packet:**
   - In the display filter bar, enter appropriate filter criteria
   - Look for HTTP POST requests containing form data
   - Press **Enter** to apply the filter

<details>
<summary>🔍 View Traffic Filtering</summary>
<br>
<p align="center">
  <img width="600" alt="Wireshark display filter for HTTP POST packets" src="https://github.com/user-attachments/assets/9feaba3d-7443-4b27-ad5c-96c0cd9076e0" />
</p>
</details>

---

### Step 4: Inspect the Packet to Find Credentials

**🎯 Purpose:** Analyze captured packets to extract plaintext credentials.

**📋 Instructions:**

1. **📋 In the filtered packet list, locate a packet with information like:**
   - `POST /userinfo.php` or similar endpoint
   - HTTP protocol designation

2. **🔍 Select the relevant packet to view its details.**

3. **📂 In the Packet Details pane, expand the following sections:**
   - **Hypertext Transfer Protocol**
   - **HTML Form URL Encoded**

4. **👁️ Inside the "HTML Form URL Encoded" section:**
   - You will see the credentials transmitted in plaintext
   - Username and password are clearly visible

<details>
<summary>🚨 View Credential Extraction</summary>
<br>
<p align="center">
  <img width="856" alt="Packet details showing plaintext credentials in HTTP form data" src="https://github.com/user-attachments/assets/da7fe228-4fa9-4c43-805a-ed1b2129a955" />
</p>
</details>

---

## ✅ Result

The experiment successfully demonstrates the interception of login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network.

🎯 **Key Achievements:**
- ✅ Successfully configured Wireshark for network packet capture
- ✅ Captured live network traffic during login attempt
- ✅ Applied appropriate filters to isolate HTTP POST requests
- ✅ Successfully extracted plaintext credentials from network packets
- ✅ Demonstrated the security vulnerability of HTTP protocol
- ✅ Documented the complete packet analysis workflow

**📊 Analysis Summary:**
- 🔍 **Protocol Analysis:** HTTP POST request containing form data
- 📝 **Data Extraction:** Clear text username and password identification
- 🚨 **Security Finding:** Credentials transmitted without encryption
- 🌐 **Network Forensics:** Complete packet-level analysis of authentication flow

**🛡️ Security Implications:**
This result confirms the inherent security flaw of the **HTTP protocol**:
- 🚨 **Vulnerability:** Any sensitive data sent over HTTP is transmitted in plaintext
- 🎯 **Risk Level:** High - credentials easily intercepted by attackers
- 🔓 **Exposure:** Network traffic accessible to anyone monitoring the network
- ⚠️ **Impact:** Complete compromise of user authentication credentials

---

## 📝 Notes

⚠️ **Ethical Considerations:** Only perform packet capture analysis on networks you own or have explicit permission to monitor. Unauthorized network monitoring is illegal in many jurisdictions.

🔒 **Legal Compliance:** Ensure all testing is conducted in controlled environments or with proper authorization. The demo website used is specifically designed for security testing purposes.

🛡️ **Security Best Practices:**
- Always use HTTPS for transmitting sensitive data
- Implement proper SSL/TLS encryption for web applications
- Never transmit passwords in plaintext
- Use secure authentication mechanisms (OAuth, SAML, etc.)
- Regular security audits of network communications

💡 **Network Analysis Tips:**
- **Display Filters:** Master Wireshark's filter syntax for efficient analysis
- **Protocol Hierarchy:** Use Statistics → Protocol Hierarchy for traffic overview
- **Follow Streams:** Right-click packets and "Follow TCP Stream" for complete conversations
- **Time Analysis:** Use time-based filters to focus on specific periods

🔧 **Advanced Wireshark Features:**
- **Deep Packet Inspection:** Analyze application layer protocols
- **Statistical Analysis:** Generate network usage reports and graphs
- **Export Objects:** Extract files transmitted over HTTP/FTP
- **Decrypt Traffic:** Analyze encrypted traffic with proper certificates

⚡ **Common Filter Examples:**
- `http.request.method == "POST"` - Show only HTTP POST requests
- `tcp.port == 80` - Show traffic on port 80 (HTTP)
- `ip.addr == 192.168.1.100` - Show traffic to/from specific IP
- `dns` - Show only DNS traffic

🎯 **Professional Applications:**
- **Network Troubleshooting:** Identify connectivity and performance issues
- **Security Analysis:** Detect suspicious network activity and intrusions
- **Forensic Investigation:** Analyze network evidence in incident response
- **Compliance Auditing:** Verify proper encryption and data handling

---

**🔗 Related Tools:**
- [tcpdump](https://www.tcpdump.org/) - Command-line packet analyzer
- [NetworkMiner](https://www.netresec.com/?page=NetworkMiner) - Network forensic analysis tool
- [Nmap](https://nmap.org/) - Network discovery and security auditing
- [Burp Suite](https://portswigger.net/burp) - Web application security testing

---

*📅 Last Updated: October 2025*
*👨‍💻 Author: Digital Forensics Lab*
