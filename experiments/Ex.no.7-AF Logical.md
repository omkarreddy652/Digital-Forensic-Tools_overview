# Ex.No.7 — AFLogical OSE: Extract Data from Android Devices

![AFLogical OSE](https://img.shields.io/badge/Tool-AFLogical%20OSE-green)
![Platform](https://img.shields.io/badge/Platform-Android-orange)
![Type](https://img.shields.io/badge/Analysis-Logical%20Extraction-blue)

---

## 📑 Table of Contents
- [🎯 Aim](#-aim)
- [📝 Description](#-description)
- [🛠️ Prerequisites & Installation](#️-prerequisites--installation)
- [📋 Procedure](#-procedure)
  - [Step 1: Initial Setup & File Extraction](#step-1-initial-setup--file-extraction)
  - [Step 2: Configure System Environment (PATH)](#step-2-configure-system-environment-path)
  - [Step 3: Install Google USB Driver (Windows Specific)](#step-3-install-google-usb-driver-windows-specific)
  - [Step 4: Prepare the Android Device (Developer Options)](#step-4-prepare-the-android-device-developer-options)
  - [Step 5: Establish and Verify ADB Connection](#step-5-establish-and-verify-adb-connection)
  - [Step 6: Deploy AFLogical OSE to the Device](#step-6-deploy-aflogical-ose-to-the-device)
  - [Step 7: Execute Logical Data Extraction](#step-7-execute-logical-data-extraction)
  - [Step 8: Collect Extracted Data (Pull to PC)](#step-8-collect-extracted-data-pull-to-pc)
- [✅ Result](#-result)
- [🔗 Reference Links](#-reference-links)
- [📝 Notes](#-notes)

---

## 🎯 Aim
To use **AFLogical OSE (Open Source Edition)** for logical extraction of data from Android devices, retrieving key user data such as contacts, call logs, and SMS messages without requiring root access.

---

## 📝 Description
**AFLogical OSE (Open Source Edition)** is a specialized forensic tool designed for logical extraction of data from Android devices. This technique retrieves key user data—like contacts, call logs, and SMS messages—by leveraging the Android OS API, and does so typically without requiring root access. It is a fundamental component of the **Open Source Android Forensics toolkit**, essential for investigations and academic studies.

---

## 🛠️ Prerequisites & Installation

### **📦 Required Files (Pre-requisites)**
- **🔧 Android Platform Tools (ADB):** For device communication
- **📱 AFLogical OSE ZIP (Source/APK):** The core forensic tool
- **💻 Google USB Driver (for Windows):** To ensure PC-device connectivity

---

## 📋 Procedure

### Step 1: Initial Setup & File Extraction

**🎯 Purpose:** Set up the working environment and extract necessary files.

**📋 Instructions:**
1. **📁 Create the primary lab folder:**
   ```bash
   C:\DF
   ```

2. **📦 Extract all downloaded ZIP archives into this folder:**
   ```bash
   C:\DF\platform-tools\
   C:\DF\aflogical-ose\
   C:\DF\usb-driver\
   ```

3. **⚠️ Note on APK:**  
   If the AFLogical OSE ZIP doesn't include the `AFLogical-OSE.apk`, use a digital forensics OS like **Santoku Linux** to extract or build the APK from the source code.


---

### Step 2: Configure System Environment (PATH)

**🎯 Purpose:** To enable the execution of `adb` commands directly from any Command Prompt or PowerShell window without specifying the full directory path.

**📋 Steps:**
1. **⚙️ Navigate to:**  
   **Control Panel → System → Advanced system settings → Environment Variables**

2. **📝 Under *User Variables*, select **Path** and click **Edit**.**

3. **➕ Click **New** and add the path:**
   ```bash
   C:\DF\platform-tools
   ```

<details>
<summary>🖼️ View Environment Variables Setup</summary>
<br>
<p align="center">
  <img width="610" height="673" alt="Environment Variables Configuration" src="https://github.com/user-attachments/assets/bf3d4690-98b2-4afc-9dcc-1b88deef2e71" />
</p>
</details>

4. **✅ Click **OK** to save.**

**🔍 Verification:**
Open a Command Prompt and run:
```bash
adb version
```

<details>
<summary>💻 View ADB Version Output</summary>
<br>
<p align="center">
  <img width="1285" height="347" alt="ADB Version Command Output" src="https://github.com/user-attachments/assets/c16b02ed-1e48-4946-a562-043abb3e9e25" />
</p>
</details>

**✅ Expected Output:**  
Displays the ADB version number (e.g., *Android Debug Bridge version 1.0.41*).

---

### Step 3: Install Google USB Driver (Windows Specific)

**🎯 Purpose:** This driver allows Windows to identify and communicate with the connected Android device via ADB.

**📋 Steps:**
1. **🔌 Connect the Android phone via USB.**
2. **🔧 Open **Device Manager** and locate the phone.**
3. **🖱️ Right-click → **Update Driver** → **Browse my computer for drivers**.**
4. **📂 Specify:**
   ```bash
   C:\DF\usb-driver
   ```
5. **➡️ Click **Next** to install.**

**🔍 Verification:**
Run:
```bash
adb devices
```

<details>
<summary>📱 View Device Connection Status</summary>
<br>
<p align="center">
  <img width="858" height="157" alt="ADB Devices Command Output" src="https://github.com/user-attachments/assets/f84a2449-99e1-4a7f-8854-58f2964be372" />
</p>
</details>

**✅ Expected Output:**  
Device listed without 'offline' or 'no permissions' status.

---

### Step 4: Prepare the Android Device (Developer Options)

**🎯 Purpose:** Enable developer features required for ADB communication.

**📋 Steps:**
1. **📱 On the device:**  
   **Settings → About phone → Tap "Build number" 7 times**

2. **🔙 Go back to **Settings → Developer options**.**

3. **✅ Enable:**
   - 🔧 USB Debugging  
   - 📦 Install via USB (if available)

<details>
<summary>📱 View Developer Options</summary>
<br>
<p align="center">
  <img width="400" alt="Android Developer Options Screen" src="https://github.com/omkarreddy652/digital-forensic-tools_overview/blob/main/images/placeholder.txt?raw=true" />
</p>
</details>

---

### Step 5: Establish and Verify ADB Connection

**🎯 Purpose:** To confirm a stable, authorized communication channel between the PC and Android device.

**📋 Steps:**
1. **🔌 Ensure the phone is connected.**
2. **💻 Run:**
   ```bash
   adb devices
   ```
3. **📱 Tap **Allow** on the phone when prompted.**

**✅ Expected Output:**

<details>
<summary>🔗 View Authorized Connection</summary>
<br>
<p align="center">
  <img width="858" height="157" alt="ADB Authorized Device Connection" src="https://github.com/user-attachments/assets/3bebf98b-8dab-4d04-ba44-1dc70d7d2d62" />
</p>
</details>

**🔧 Troubleshooting:**  
If *unauthorized*, replug cable and tap **Allow** again.

---

### Step 6: Deploy AFLogical OSE to the Device

**🎯 Purpose:** Transfer and install the forensic APK onto the Android device.

**📋 Steps:**
1. **📁 Ensure APK is located at:**
   ```bash
   C:\DF\aflogical-ose\AFLogical-OSE.apk
   ```

2. **📦 Install it:**
   ```bash
   adb install --bypass-low-target-sdk-block "C:\Users\Manya\Downloads\DF\ForensicLab\AFLogical-OSE_1.5.2.apk"
   ```

<details>
<summary>📱 View APK Installation</summary>
<br>
<p align="center">
  <img width="1464" height="183" alt="AFLogical OSE APK Installation" src="https://github.com/user-attachments/assets/b02f289c-3de4-42f5-90c1-518131a6e4f7" />
</p>
</details>

---

### Step 7: Execute Logical Data Extraction

**🎯 Purpose:** Initiate data retrieval using AFLogical.

**📋 Steps:**
1. **📱 Open **AFLogical** on the device.**
2. **🔐 Grant permissions (Contacts, SMS, Call Logs, Storage).**
3. **✅ Select:**
   - 👥 Contacts  
   - 💬 SMS  
   - 📞 Call Logs  
   - 🖼️ MMS  
   - 📅 Calendar

4. **▶️ Tap **Start Extraction**.**
5. **⏳ Wait until extraction completes.**

**📂 Default Save Location:**
```bash
/sdcard/aflogical/
```
or
```bash
/storage/emulated/0/aflogical/
```

<details>
<summary>📱 View AFLogical Interface</summary>
<br>
<p align="center">
  <img width="400" alt="AFLogical OSE Extraction Interface" src="https://github.com/omkarreddy652/digital-forensic-tools_overview/blob/main/images/placeholder.txt?raw=true" />
</p>
</details>

---

### Step 8: Collect Extracted Data (Pull to PC)

**🎯 Purpose:** Transfer extracted files from the device to the PC.

**💻 Command:**
```bash
adb pull /sdcard/aflogical C:\Users\Manya\Downloads
```

<details>
<summary>📥 View Data Transfer</summary>
<br>
<p align="center">
  <img width="1358" height="173" alt="ADB Pull Command Execution" src="https://github.com/user-attachments/assets/545baf69-e750-410a-b07a-657d60b91e97" />
</p>
</details>

**🔍 Verification:**
Files saved to:
```bash
C:\Users\Manya\Downloads
```

<details>
<summary>📁 View Extracted Files</summary>
<br>
<p align="center">
  <img width="1254" height="361" alt="Extracted Files in Downloads Folder" src="https://github.com/user-attachments/assets/22f021cb-f711-4268-88cb-eba0ed6c5684" />
</p>
</details>

---

## ✅ Result

By following these steps, we successfully used AFLogical OSE to perform logical data extraction from an Android device.

🎯 **Key Achievements:**
- ✅ Successfully configured ADB environment and established device communication
- ✅ Installed and deployed AFLogical OSE APK to the target Android device
- ✅ Performed logical extraction of key user data (contacts, SMS, call logs, MMS, calendar)
- ✅ Successfully transferred extracted data from device to PC for analysis
- ✅ Completed forensic extraction without requiring root access on the device

**📊 Data Retrieved:**
- 👥 **Contacts:** Complete contact database with names, numbers, and details
- 💬 **SMS Messages:** Text message history with timestamps and metadata
- 📞 **Call Logs:** Incoming, outgoing, and missed call records
- 🖼️ **MMS:** Multimedia message data and attachments
- 📅 **Calendar:** Calendar events and appointments

---

## 🔗 Reference Links

- **🔧 Android Platform Tools (ADB):** [https://developer.android.com/tools/releases/platform-tools](https://developer.android.com/tools/releases/platform-tools)
- **🐧 Santoku Linux (Source for AFLogical OSE):** [https://sourceforge.net/projects/santoku/](https://sourceforge.net/projects/santoku/)
- **💻 Google USB Driver (Windows):** [https://developer.android.com/studio/run/win-usb](https://developer.android.com/studio/run/win-usb)

---

## 📝 Notes

⚠️ **Legal Compliance:** Always ensure you have proper authorization before performing forensic extraction on any device. This tool should only be used for legitimate forensic investigations, academic research, or on devices you own.

🔒 **Data Security:** Handle extracted data with appropriate security measures. Forensic data may contain sensitive personal information that must be protected according to relevant privacy laws and regulations.

📱 **Device Compatibility:** AFLogical OSE works best with Android devices running older versions. Some newer Android versions may have enhanced security features that limit logical extraction capabilities.

🔍 **Further Analysis:** The extracted data can be analyzed using various forensic tools such as:
- **Autopsy** - Open source digital forensics platform
- **MSAB XRY Mobile Forensics** - Commercial mobile forensics solution
- **Cellebrite UFED** - Professional mobile forensic extraction tool

---

**🔗 Related Tools:**
- [Autopsy](https://www.autopsy.com/) - Digital forensics platform
- [Volatility](https://www.volatilityfoundation.org/) - Memory forensics framework
- [SIFT Workstation](https://digital-forensics.sans.org/community/downloads) - Forensic analysis toolkit

---

*📅 Last Updated: October 2025*
*👨‍💻 Author: Digital Forensics Lab*
