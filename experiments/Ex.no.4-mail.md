# Ex.No.4 — Mail Header Analyzer (MHA)

![MHA](https://img.shields.io/badge/Tool-Mail%20Header%20Analyzer-green)
![Platform](https://img.shields.io/badge/Platform-Web--Based-orange)
![Type](https://img.shields.io/badge/Analysis-Email%20Forensics-blue)

**📚 Course / Lab:** Digital Forensics Lab  
**🔢 Experiment No.:** 4  
**📝 Title:** Mail Header Analyzer (MHA)

---

## 📑 Table of Contents

- [Ex.No.4 — Mail Header Analyzer (MHA)](#exno4--mail-header-analyzer-mha)
  - [📑 Table of Contents](#-table-of-contents)
  - [🎯 Aim](#-aim)
  - [🛠️ Requirements](#️-requirements)
  - [📝 Description](#-description)
  - [🌐 Website Used](#-website-used)
  - [📋 Procedure](#-procedure)
    - [Step 1: Get the Email Header](#step-1-get-the-email-header)
    - [Step 2: Use a Mail Header Analyzer (MHA)](#step-2-use-a-mail-header-analyzer-mha)
    - [Step 3: Analyze The Report](#step-3-analyze-the-report)
    - [Step 4: Investigate Email Path and Records](#step-4-investigate-email-path-and-records)
  - [🔍 Technical Info for Deeper Analysis](#-technical-info-for-deeper-analysis)
  - [✅ Email Header Analysis Result](#-email-header-analysis-result)
    - [Email Subject](#email-subject)
    - [Authentication Status](#authentication-status)
    - [Delivery & Relay Information](#delivery--relay-information)
    - [Additional Header Insights](#additional-header-insights)
    - [Technical Summary](#technical-summary)
    - [Security Notes](#security-notes)
  - [📝 Notes](#-notes)

---

## 🎯 Aim

To use a **Mail Header Analyzer (MHA)** to trace an email's origin and verify its authenticity by examining its header for signs of spoofing, analyzing authentication mechanisms (SPF, DKIM, DMARC), and understanding the email delivery path for forensic investigation purposes.

---

## 🛠️ Requirements

- **💻 Computer with internet access**
- **📧 Email client** (Gmail, Outlook, Thunderbird, etc.)
- **🌐 Web browser** for accessing online MHA tools
- **📋 Sample email** for header analysis
- **🔍 Online Mail Header Analyzer** tool access

---

## 📝 Description

Mail Header Analyzer (MHA) is a crucial forensic tool used to examine email headers and trace the origin, authenticity, and delivery path of emails. It helps investigators identify email spoofing, verify sender authenticity, analyze authentication protocols (SPF, DKIM, DMARC), and understand the complete journey of an email through various mail servers. This analysis is essential for email forensics, spam detection, and cybersecurity investigations.

---

## 🌐 Website Used

**🔗 Analysis Tool:** [xheaders.com](https://xheaders.com/)

⚠️ **Note:** This is a professional mail header analysis service that provides comprehensive email authentication and delivery path analysis.

---

## 📋 Procedure

### Step 1: Get the Email Header

**🎯 Purpose:** Extract the complete raw email header for analysis.

**📋 Instructions:**

1. **📧 Open your email client and locate the target email.**

2. **📋 Copy the full, raw header from your email client:**

   **For Gmail:**
   - Open the email
   - Click the three dots (⋮) menu
   - Select **"Show original"**

3. **💡 UX Features:**
   - Smooth fade-in animation when displaying the header pane
   - Single-button text selection with animated "Copied!" notification

<details>
<summary>📧 View Email Header Extraction (Gmail)</summary>
<br>
<p align="center">
  <img width="620" alt="Gmail email header extraction process" src="https://github.com/user-attachments/assets/8a9185a5-1c37-4d98-839e-d1f4edaeddff" />
</p>
</details>

4. **📄 View the original message with complete headers:**

<details>
<summary>📝 View Original Message Headers</summary>
<br>
<p align="center">
  <img width="600" alt="Complete email headers and original message" src="https://github.com/user-attachments/assets/5607c1ac-bbbf-4155-9233-5deda972133c" />
</p>
</details>

---

### Step 2: Use a Mail Header Analyzer (MHA)

**🎯 Purpose:** Analyze the extracted email headers using professional tools.

**📋 Instructions:**

1. **🌐 Navigate to the online analyzer:** [xheaders.com](https://xheaders.com/)

2. **📋 Paste the complete email header into the analysis field.**

3. **🔍 Click "Analyze" to process the headers.**

4. **💫 UI Features:**
   - Progress bar animation during header parsing
   - Animated results reveal
   - Color-coded results (green for pass, red for fail)
   - Micro-animations with icons and checkmarks

<details>
<summary>🔍 View Mail Header Analysis Interface</summary>
<br>
<p align="center">
  <img width="845" alt="xheaders.com mail header analyzer interface" src="https://github.com/user-attachments/assets/8014395c-927d-40e0-a47f-5739eb6ec118" />
</p>
</details>

---

### Step 3: Analyze The Report

**🎯 Purpose:** Review authentication results and identify potential security issues.

**📋 Key Analysis Points:**

1. **🔐 Review SPF, DKIM, and DMARC results:**
   - Animated icons provide instant feedback
   - Interactive tooltips explain each authentication method
   - Slide-down animations for detailed results

2. **📊 Authentication Status Indicators:**
   - ✅ **Pass:** Green checkmarks with pulse animation
   - ❌ **Fail:** Red X marks with shake animation
   - ⚠️ **Warning:** Yellow indicators for partial compliance

<details>
<summary>📊 View Authentication Analysis Results</summary>
<br>
<p align="center">
  <img width="745" alt="SPF, DKIM, and DMARC authentication results" src="https://github.com/user-attachments/assets/be240843-f7bf-41c3-a537-c615ee210213" />
</p>
</details>

**📋 Review the Overall Delivery Summary:**
- DMARC, SPF, and DKIM compliance status
- Animated highlights for passes and failures
- Color-coded status indicators

---

### Step 4: Investigate Email Path and Records

**🎯 Purpose:** Trace the complete email delivery path and verify server authenticity.

**📋 Investigation Points:**

1. **🛣️ Trace the email delivery path:**
   - Animated email journey flowchart
   - Interactive nodes with hover effects
   - Explanatory popups for each relay point

2. **🔍 Verify authorized servers and routing:**
   - Confirm sender server authorization
   - Analyze relay chain for anomalies
   - Check for suspicious routing patterns

<details>
<summary>🛣️ View Email Delivery Path Analysis</summary>
<br>
<p align="center">
  <img width="650" alt="Email delivery path and server routing analysis" src="https://github.com/user-attachments/assets/05be300a-fa22-4c2d-8ef5-fab16573c27a" />
</p>
</details>

---

## 🔍 Technical Info for Deeper Analysis

**📋 Key Header Components:**

| Component | Description | Forensic Significance |
|-----------|-------------|----------------------|
| **From/To/Subject/Date** | Basic sender/receiver and timestamp information | Identity verification and timeline analysis |
| **Received** | Tracks journey across mail servers | Helps trace spoofing or relay problems |
| **Return-Path/Reply-To** | Shows bounce or reply addresses | Used for authenticity checks and sender verification |
| **SPF, DKIM, DMARC** | Authentication mechanisms | Crucial for anti-spoofing and trust verification |
| **MIME-Version/Content-Type** | Email format and content support | Content analysis and attachment verification |
| **Message-ID** | Unique identifier for each email | Useful for tracking and diagnostic purposes |
| **X-Spam-Score/X-Mailer** | Spam risk and mail client information | Security assessment and client identification |

---

## ✅ Email Header Analysis Result

### Email Subject
**📧 Subject:** Reset your Olympus password

---

### Authentication Status

**🔐 Email Authentication Summary:**

| Method | Result | Details |
|--------|--------|---------|
| **SPF** | ✅ **Pass** | The sending server (149.72.189.153) is authorized for the domain |
| **DKIM** | ✅ **Pass** | DKIM signature verified; email unchanged and signed with sender's key |
| **DMARC** | ✅ **Pass** | DMARC policy enforced and authentication checks aligned |

**🔑 DKIM Authentication Details:**
- **Status:** ✅ **PASS**
- **Domain:** `greatlearning.in`
- **Selector:** `s1`
- **Algorithm:** `rsa-sha256`
- **Signed Headers:** date, from, subject, mime-version, content-type, to, etc.
- **Verification:** Email content has not been tampered with since signing

---

### Delivery & Relay Information

**📊 Email Routing Analysis:**

**🛣️ Email Path Summary:**
- **Originating Server:** `olympus.greatlearning.in` (149.72.189.153)
- **Relay Service:** `wrqvbdww.outbound-mail.sendgrid.net`
- **Final Destination:** Google's servers (`mx.google.com`)
- **Total Delay:** 1 second
- **Originating IP:** Not found in header (privacy feature)

**📋 Detailed Hop Analysis:**

| Hop | Delay | From Server | Relay Info |
|-----|-------|-------------|------------|
| 1 | 0s | olympus.greatlearning.in | geopod-ismtpd-18 (ESMTP) |
| 2 | 0s | recvd-5fb5cd787f-5wk2n | SMTP relay |
| 3 | 0s | wrqvbdww.outbound-mail.sendgrid.net | mx.google.com (TLS encrypted) |
| 4 | 0s | 2002:ac8:5fc4:0:b0:4ae:f855:77b0 | SMTP relay |
| 5 | * | 2002:a05:7010:7acd:b0:485:30c4:c8bc | SMTP |

---

### Additional Header Insights

**⚠️ Notable Findings:**

- **SPF Alignment:** Minor misalignment detected, but DKIM compensates
- **Sender Mismatch:** From address doesn't match Return-Path (potential forwarding scenario)
- **X-Mailer/User-Agent:** Not present in headers
- **Spam Score:** Not available in analysis
- **Blacklist Status:** No blacklist detections for sender IP

---

### Technical Summary

**🔐 Authentication Protocol Analysis:**

- **📧 SPF (Sender Policy Framework):** Verifies that the sending server is authorized to send emails for the domain
- **🔑 DKIM (DomainKeys Identified Mail):** Ensures email content is unchanged and digitally signed by a valid sender key
- **🛡️ DMARC (Domain-based Message Authentication):** Enforces policies requiring SPF or DKIM alignment with the visible domain

**✅ Authentication Result:** All three methods report **PASS** - message verified as authentic and safe

---

### Security Notes

**🛡️ Security Assessment:**

- ✅ **Blacklist Status:** No blacklists detected for sender IP
- ✅ **Authentication:** SPF/DKIM/DMARC all passed validation
- ✅ **Legitimacy:** High confidence in sender authenticity
- ⚠️ **Minor Issues:** Address mismatches likely due to legitimate email relays
- ✅ **Tampering:** No signs of content modification or spoofing detected

**🔍 Conclusion:**
The email is fully authenticated and DMARC compliant. Both SPF and DKIM passed validation successfully. Minor sender address mismatches are not a security threat due to successful cryptographic verification and recognized relay services. No indicators of spoofing, blacklisting, or content tampering detected.

---

## 📝 Notes

⚠️ **Privacy Considerations:** Email header analysis may reveal sensitive routing information. Ensure proper authorization before analyzing headers from third parties.

🔒 **Legal Compliance:** Email forensics should be conducted only with proper legal authority or on emails you own. Respect privacy laws and regulations.

🛡️ **Authentication Best Practices:**
- Implement SPF records for domain authorization
- Configure DKIM signing for email integrity
- Enforce DMARC policies for comprehensive protection
- Regular monitoring of authentication failures
- Maintain updated DNS records for email security

💡 **Analysis Tips:**
- **Header Sequence:** Analyze headers in chronological order (bottom to top)
- **Time Zones:** Pay attention to timestamp inconsistencies
- **IP Geolocation:** Verify sender location matches expected geography
- **Relay Patterns:** Identify unusual or suspicious routing paths

🔧 **Advanced Analysis Techniques:**
- **Message-ID Patterns:** Analyze for spoofing indicators
- **Received Header Analysis:** Trace complete delivery chain
- **Authentication Alignment:** Verify domain alignment across protocols
- **Reputation Checking:** Cross-reference sender IPs with threat intelligence

⚡ **Common Spoofing Indicators:**
- Missing or invalid authentication records
- Suspicious relay patterns or geographic inconsistencies
- Mismatched sender domains and authentication domains
- Unusual header formatting or missing standard fields

🎯 **Professional Applications:**
- **Incident Response:** Email-based attack investigation
- **Threat Hunting:** Identifying malicious email campaigns
- **Compliance Auditing:** Verifying email security controls
- **Forensic Investigation:** Legal evidence collection and analysis

---

**🔗 Related Tools:**
- [MX Toolbox](https://mxtoolbox.com/) - Email server and DNS analysis
- [Mail-Tester](https://www.mail-tester.com/) - Email deliverability testing
- [SPF Record Checker](https://www.kitterman.com/spf/validate.html) - SPF validation
- [DMARC Analyzer](https://www.dmarcanalyzer.com/) - DMARC policy analysis

---

*📅 Last Updated: October 2025*
*👨‍💻 Author: Digital Forensics Lab*
