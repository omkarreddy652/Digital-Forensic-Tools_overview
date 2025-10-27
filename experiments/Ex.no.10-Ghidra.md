# Ex.No.10 — Use Ghidra to Disassemble and Analyze Malware Code

![Ghidra](https://img.shields.io/badge/Tool-Ghidra-green)
![Platform](https://img.shields.io/badge/Platform-Cross--Platform-orange)
![Type](https://img.shields.io/badge/Analysis-Malware%20Analysis-blue)

**📚 Course / Lab:** Digital Forensics Lab  
**🔢 Experiment No.:** 10  
**📝 Title:** Use Ghidra to Disassemble and Analyze the Malware Code

---

## 📑 Table of Contents

- [Ex.No.10 — Use Ghidra to Disassemble and Analyze Malware Code](#exno10--use-ghidra-to-disassemble-and-analyze-malware-code)
  - [📑 Table of Contents](#-table-of-contents)
  - [🎯 Project Objectives](#-project-objectives)
  - [🛠️ Prerequisites](#️-prerequisites)
  - [📋 Project Outline (GitHub Repository Components)](#-project-outline-github-repository-components)
    - [1. Repository Root](#1-repository-root)
    - [2. Tutorial Steps](#2-tutorial-steps)
      - [A. Environment Setup](#a-environment-setup)
      - [B. Initial Analysis](#b-initial-analysis)
      - [C. Function Analysis](#c-function-analysis)
      - [D. String and Import Analysis](#d-string-and-import-analysis)
      - [E. Advanced Techniques (Optional)](#e-advanced-techniques-optional)
    - [3. Example Automation Scripts](#3-example-automation-scripts)
    - [4. Sample Data](#4-sample-data)
    - [5. Report Template](#5-report-template)
  - [✅ Result](#-result)
  - [📝 Notes](#-notes)

---

## 🎯 Project Objectives

- **🔍 To provide a hands-on guide to disassembling and analyzing malware with **Ghidra**.**
- **🛡️ To enable readers to recognize common malware functionalities, such as **persistence mechanisms**, **anti-analysis techniques**, and **network communications**.**
- **⚙️ To equip users with the skills to interpret low-level assembly code and understand high-level behaviors using Ghidra's decompiler.**

---

## 🛠️ Prerequisites

- **🔧 Ghidra:** Installed and configured (requires Java Development Kit - JDK)
- **💻 Virtual Machine (VM):** A secure, isolated, and virtualized environment (e.g., VMWare, VirtualBox) to safely handle binaries
- **📁 Sample Binary:** A benign sample or a controlled, safe hex dump for analysis (due to ethical/safety concerns)

---

## 📋 Project Outline (GitHub Repository Components)

A typical project structure for this analysis exercise would include the following components:

### 1. Repository Root

**🗂️ Project Structure:**

| File/Folder | Description |
| :--- | :--- |
| `README.md` | Provides an overview of Ghidra, project requirements, and an outline of the analysis tutorial |
| `templates/` | Contains the template for documenting the forensic analysis findings |
| `docs/` | Contains the step-by-step analysis tutorials |
| `scripts/` | Stores automation scripts for Ghidra (Python/Java) |
| `samples/` | Stores the benign sample binaries or hex dumps for practice |

---

### 2. Tutorial Steps

**📋 Step-by-step instructions on performing static analysis using Ghidra:**

#### A. Environment Setup

**🎯 Purpose:** Set up a secure analysis environment for malware examination.

**📋 Instructions:**
- Instructions for setting up a virtualized and isolated analysis environment
- Guide on installing Ghidra and verifying the Java dependency

<details>
<summary>🖥️ View Environment Setup</summary>
<br>
<p align="center">
  <img width="700" alt="Ghidra environment setup and configuration" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.18.png" />
</p>
</details>

#### B. Initial Analysis

**🎯 Purpose:** Load the binary into Ghidra and perform initial analysis.

**📋 Key Components:**
- **📥 Loading the Binary:** How to launch Ghidra, create a new project, and import the sample binary
- **🔄 Auto-Analysis:** How to run the initial Ghidra auto-analysis and select appropriate analyzers
- **🎯 Identifying Entry Points:** Locating the main function or the binary's execution starting point

<details>
<summary>📊 View Binary Loading Process</summary>
<br>
<p align="center">
  <img width="700" alt="Ghidra binary import and project creation" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.15.png" />
</p>
</details>

<details>
<summary>🔍 View Auto-Analysis Configuration</summary>
<br>
<p align="center">
  <img width="700" alt="Ghidra auto-analysis settings and options" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.14.png" />
</p>
</details>

#### C. Function Analysis

**🎯 Purpose:** Analyze individual functions and understand their behavior.

**📋 Key Components:**
- **🔧 Decompilation:** Using Ghidra's Decompiler window to translate assembly into high-level C-like code
- **🏷️ Function Identification:** Methods for renaming and analyzing critical functions to understand their purpose
- **🔗 Cross-Referencing (XREF):** Utilizing Ghidra's cross-referencing features to trace where a function is called or where a variable is used

<details>
<summary>⚙️ View Function Decompilation</summary>
<br>
<p align="center">
  <img width="700" alt="Ghidra decompiler showing C-like code from assembly" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.11.png" />
</p>
</details>

<details>
<summary>🔍 View Cross-Reference Analysis</summary>
<br>
<p align="center">
  <img width="700" alt="Cross-reference analysis and function tracing" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.10.png" />
</p>
</details>

#### D. String and Import Analysis

**🎯 Purpose:** Identify malicious indicators through strings and imported functions.

**📋 Key Components:**
- **📝 Locating Strings:** Using the **Defined Strings** window to find meaningful static strings (e.g., URLs, file paths, registry keys) that indicate malicious behavior
- **📦 Interpreting Imports:** Analyzing the **Import Table** to identify relevant imported functions (e.g., `CreateFileA`, `URLDownloadToFile`, `RegSetValueEx`) that suggest malware functionality

<details>
<summary>📝 View String Analysis</summary>
<br>
<p align="center">
  <img width="700" alt="String analysis and identification of suspicious text" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.9.png" />
</p>
</details>

<details>
<summary>📦 View Import Table Analysis</summary>
<br>
<p align="center">
  <img width="700" alt="Import table showing suspicious API functions" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.7.png" />
</p>
</details>

#### E. Advanced Techniques (Optional)

**🎯 Purpose:** Utilize advanced Ghidra features for comprehensive analysis.

**📋 Advanced Features:**
- **📈 Control Flow Graphs (CFGs):** Visualizing program execution flow
- **🤖 Custom Scripts:** Writing and running custom Ghidra scripts (Python/Java) for automation

---

### 3. Example Automation Scripts

**🤖 Scripts using Ghidra's API to automate repetitive analysis tasks:**

| Script Example | Purpose |
| :--- | :--- |
| `extract_strings.py` | Automates the extraction and listing of all unique string references in the binary |
| `network_analysis.py` | Identifies and flags functions that contain network-related API calls (e.g., `socket`, `connect`, `send`) |
| `label_functions.py` | Automates the labeling of functions and data segments based on known malicious patterns (e.g., file system manipulation, registry edits) |

---

### 4. Sample Data

**📁 Safe practice files for malware analysis training:**

- **🔒 Benign Binary or Hex Dump:** Provide safe files for users to practice the disassembly steps
  - *Example:* `benign_sample1.bin` (A simple C program that mimics system calls or file writing but contains no harmful payload)

<details>
<summary>📁 View Sample Binary Analysis</summary>
<br>
<p align="center">
  <img width="700" alt="Analysis of benign sample binary" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.4.png" />
</p>
</details>

<details>
<summary>🔍 View Binary Structure</summary>
<br>
<p align="center">
  <img width="700" alt="Binary structure and memory layout" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.3.png" />
</p>
</details>

<details>
<summary>📊 View Assembly Code Analysis</summary>
<br>
<p align="center">
  <img width="700" alt="Assembly code disassembly and analysis" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/97de06473d645e6627f8ffd9004efdb5c19742a8/images/10.2.png" />
</p>
</details>

---

### 5. Report Template

**📝 A template to structure and document the findings of the Ghidra analysis:**

**📋 Report Structure:**

1. **📄 Summary of Analysis:** Brief description of the suspected malware and the scope of the analysis
2. **⚙️ Function Analysis:** Detailed summary of key functions, their purpose, and forensic findings
3. **🚨 Behavioral Indicators:** Summary of observed behaviors (e.g., persistence, communication protocols, anti-analysis checks)
4. **💡 Recommendations:** Suggestions for containment, eradication, or further analysis (e.g., dynamic analysis)

---

## ✅ Result

The experiment on malware analysis using Ghidra was successfully performed. The malware binary was disassembled, decompiled, and analyzed to identify its functions, strings, and behavioral patterns. This helped in understanding the internal logic, persistence mechanisms, and potential malicious activities of the code.

🎯 **Key Achievements:**
- ✅ Successfully set up a secure virtualized environment for malware analysis
- ✅ Configured and utilized Ghidra for static malware analysis
- ✅ Performed comprehensive binary disassembly and decompilation
- ✅ Identified suspicious functions, strings, and imported APIs
- ✅ Analyzed behavioral patterns and malicious indicators
- ✅ Documented findings using structured forensic reporting methodology

**📊 Analysis Summary:**
- 🔍 **Static Analysis:** Complete binary disassembly and code structure examination
- ⚙️ **Function Analysis:** Identification and documentation of critical functions
- 📝 **String Analysis:** Extraction and analysis of embedded strings and indicators
- 📦 **Import Analysis:** Examination of suspicious API calls and system interactions
- 🤖 **Automation:** Implementation of custom scripts for repetitive analysis tasks

**🛡️ Security Insights:**
- 🔒 **Persistence Mechanisms:** Identified methods used for system persistence
- 🌐 **Network Communications:** Analyzed network-related functionalities
- 🛡️ **Anti-Analysis Techniques:** Detected evasion and obfuscation methods
- 📁 **File System Operations:** Documented file creation, modification, and deletion activities

---

## 📝 Notes

⚠️ **Safety First:** Always perform malware analysis in a completely isolated virtual environment. Never analyze malware on production systems or networks.

🔒 **Virtual Machine Requirements:** Use a dedicated VM with no network connectivity or use a controlled network environment for malware analysis. Take snapshots before analysis for easy restoration.

🛡️ **Legal and Ethical Considerations:** Only analyze malware samples that you have legal permission to examine. Respect intellectual property and privacy laws.

💡 **Best Practices:**
- Always work in isolated environments
- Document all findings thoroughly
- Use version control for analysis scripts and reports
- Maintain detailed chain of custody for evidence
- Keep Ghidra and analysis tools updated

🔧 **Advanced Analysis Techniques:**
- **Dynamic Analysis** - Complement static analysis with runtime behavior examination
- **Sandbox Analysis** - Use automated sandboxes for initial behavioral assessment
- **Signature Development** - Create detection signatures based on identified patterns
- **Threat Intelligence** - Correlate findings with known threat actor TTPs

⚡ **Ghidra Advanced Features:**
- **Script Development** - Create custom analysis automation
- **Plugin Development** - Extend Ghidra functionality for specific needs
- **Collaborative Analysis** - Use Ghidra Server for team-based analysis
- **Integration** - Combine with other tools like IDA Pro, x64dbg, or Volatility

🎯 **Further Learning:**
- Reverse engineering fundamentals
- Assembly language programming
- Malware families and classifications
- Advanced persistent threat (APT) analysis techniques
- Incident response and malware containment

---

**🔗 Related Tools:**
- [IDA Pro](https://hex-rays.com/ida-pro/) - Commercial disassembler and debugger
- [x64dbg](https://x64dbg.com/) - Open-source debugger for Windows
- [Volatility](https://www.volatilityfoundation.org/) - Memory forensics framework
- [YARA](https://virustotal.github.io/yara/) - Pattern matching engine for malware identification

---

*📅 Last Updated: October 2025*
*👨‍💻 Author: Digital Forensics Lab*
