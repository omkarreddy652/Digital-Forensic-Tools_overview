# Ex.No.7 — Use AFLogical OSE to Extract Data from Android Devices

![AFLogical OSE](https://img.shields.io/badge/Tool-AFLogical%20OSE-green)
![Platform](https://img.shields.io/badge/Platform-Android-orange)
![Type](https://img.shields.io/badge/Analysis-Logical%20Extraction-blue)

**📚 Course / Lab:** Digital Forensics Lab  
**🔢 Experiment No.:** 7  
**📝 Title:** Use AFLogical OSE to Extract Data from an Android Device

---

## 📑 Table of Contents

- [Ex.No.7 — Use AFLogical OSE to Extract Data from Android Devices](#exno7--use-aflogical-ose-to-extract-data-from-android-devices)
  - [📑 Table of Contents](#-table-of-contents)
  - [📝 Description](#-description)
  - [📋 Step-by-Step Process](#-step-by-step-process)
    - [Step 1: Prepare Your Environment](#step-1-prepare-your-environment)
    - [Step 2: Connect the Android Device to Your Computer](#step-2-connect-the-android-device-to-your-computer)
    - [Step 3: Extract Data Using AFLogical OSE](#step-3-extract-data-using-aflogical-ose)
    - [Step 4: Transfer Extracted Data to Your Computer](#step-4-transfer-extracted-data-to-your-computer)
    - [Step 5: Analyze the Extracted Data](#step-5-analyze-the-extracted-data)
    - [Step 6: Clean Up](#step-6-clean-up)
  - [✅ Result](#-result)
  - [� Notes](#-notes)
    - [Step 2: Configure System Environment (PATH)](#step-2-configure-system-environment-path)
    - [Step 3: Install Google USB Driver (Windows Specific)](#step-3-install-google-usb-driver-windows-specific)
    - [Step 4: Prepare the Android Device (Developer Options)](#step-4-prepare-the-android-device-developer-options)
    - [Step 5: Establish and Verify ADB Connection](#step-5-establish-and-verify-adb-connection)
    - [Step 6: Deploy AFLogical OSE to the Device](#step-6-deploy-aflogical-ose-to-the-device)
    - [Step 7: Execute Logical Data Extraction](#step-7-execute-logical-data-extraction)
    - [Step 8: Collect Extracted Data (Pull to PC)](#step-8-collect-extracted-data-pull-to-pc)
  - [✅ Result](#-result-1)
  - [🔗 Reference Links](#-reference-links)
  - [📝 Notes](#-notes-1)

---

## 📝 Description
**AFLogical OSE (Open Source Edition)** is a tool designed for logical data extraction from Android devices. As part of the Open Source Android Forensics project, it collects non-file system data like **contacts**, **messages (SMS/MMS)**, and **call logs** without needing root access.

---

## 📋 Step-by-Step Process

### Step 1: Prepare Your Environment

**🎯 Purpose:** Set up the required tools and environment for Android data extraction.

**📋 Instructions:**

1. **📥 Download AFLogical OSE:**
   - Visit the AFLogical OSE GitHub page and download the latest release, or clone the repository using Git.

2. **☕ Install Java:**
   - AFLogical OSE requires Java to run. Ensure Java is installed on your machine.

3. **🔧 Install Android Debug Bridge (ADB):**
   - Download **ADB** (a command-line tool for device communication) from the Android Developer's website.
   - Install it on your system and **add it to your system's PATH environment variable** for easy access from the command line.

4. **📱 Enable USB Debugging on the Android Device:**
   - Go to **Settings > About Phone** and tap **Build Number seven times** to enable Developer Options.
   - Go to **Settings > Developer Options** and enable **USB Debugging**.

<details>
<summary>📱 View Developer Options Setup</summary>
<br>
<p align="center">
  <img width="600" alt="Android Developer Options setup" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.1.png" />
</p>
</details>

<details>
<summary>⚙️ View USB Debugging Configuration</summary>
<br>
<p align="center">
  <img width="600" alt="USB Debugging enabled" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.3.png" />
</p>
</details>

---

### Step 2: Connect the Android Device to Your Computer

**🎯 Purpose:** Establish a stable connection between the Android device and computer.

**📋 Instructions:**

1. **🔌 Connect via USB:**
   - Use a USB cable to connect the Android device to your computer.

2. **🔍 Verify ADB Connection:**
   - Open Command Prompt/Terminal and run the following command:
   ```bash
   adb devices
   ```
   - **✅ Verification:** The device should be listed, confirming that the ADB connection is ready.

<details>
<summary>💻 View ADB Connection Verification</summary>
<br>
<p align="center">
  <img width="700" alt="ADB devices command output" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/7bc2c6c9cc6dd5cdd9401ae3781aa66e70193dde/images/7.13.jpeg" />
</p>
</details>

---

### Step 3: Extract Data Using AFLogical OSE

**🎯 Purpose:** Install and execute AFLogical OSE on the target Android device.

**📋 Instructions:**

1. **📦 Push the APK to the Android Device:**
   - Navigate to the AFLogical OSE directory in your terminal.
   - Run the command to install the AFLogical OSE APK on the device:
   ```bash
   adb install aflogical.apk
   ```

<details>
<summary>📱 View APK Installation Process</summary>
<br>
<p align="center">
  <img width="700" alt="AFLogical APK installation" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.7.png" />
</p>
</details>

2. **🚀 Launch the AFLogical OSE App on the Device:**
   - On the Android device, open the newly installed AFLogical app.

3. **✅ Select and Start Data Extraction:**
   - Select the desired data types (e.g., contacts, SMS, MMS, call logs) from the app's options.
   - The app will start the extraction process, storing the data in **.csv files** on the device's storage, typically in a directory named `aflogical`.

<details>
<summary>📊 View Data Selection Interface</summary>
<br>
<p align="center">
  <img width="400" alt="AFLogical data selection interface" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.12.jpeg" />
</p>
</details>

<details>
<summary>⚡ View Extraction Process</summary>
<br>
<p align="center">
  <img width="400" alt="Data extraction in progress" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.11.jpeg" />
</p>
</details>

---

### Step 4: Transfer Extracted Data to Your Computer

**🎯 Purpose:** Transfer the extracted data from the Android device to your computer for analysis.

**📋 Instructions:**

1. **📥 Use ADB to Pull Data:**
   - After extraction is complete, transfer the collected data files from the Android device to your computer using the `adb pull` command:
   ```bash
   adb pull /sdcard/aflogical /path/to/destination
   ```
   - **📝 Note:** Replace `/path/to/destination` with the desired save location on your computer.

<details>
<summary>📁 View Data Transfer Process</summary>
<br>
<p align="center">
  <img width="700" alt="ADB pull command execution" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.8.png" />
</p>
</details>

2. **🔍 Verify the Data:**
   - Navigate to the destination directory and check the `.csv` files to ensure all required data has been successfully transferred.

---

### Step 5: Analyze the Extracted Data

**🎯 Purpose:** Examine and analyze the extracted data for forensic evidence.

**📋 Instructions:**

1. **📊 Open the CSV Files:**
   - Use applications like **Excel**, **Google Sheets**, or a text editor to open and analyze the `.csv` files containing the extracted logical data.

2. **📝 Review and Document:**
   - Carefully review the data for any relevant evidence or information.
   - Document all findings and prepare a comprehensive report.

<details>
<summary>📈 View Data Analysis</summary>
<br>
<p align="center">
  <img width="700" alt="CSV data analysis in spreadsheet" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/de2d7c56c138c87d4745d2dbaf512dc4e2beaedc/images/7.9.png" />
</p>
</details>

---

### Step 6: Clean Up

**🎯 Purpose:** Properly clean up the environment and remove forensic tools from the device.

**📋 Instructions:**

1. **🗑️ Uninstall AFLogical OSE:**
   - Once data extraction is complete and verified, safely uninstall the app from the Android device:
   ```bash
   adb uninstall com.viaforensics.android.aflogical
   ```

2. **🔌 Disconnect the Device:**
   - Safely disconnect the Android device from your computer.

**🎯 Summary:** By following these steps, you successfully perform a logical extraction on an Android device using AFLogical OSE, a valuable technique in digital forensic investigations.

---

## ✅ Result

The experiment using AFLogical OSE was successfully performed. The tool efficiently extracted logical data such as contacts, messages, and media files from the mobile device, demonstrating its usefulness in mobile forensic data acquisition.

🎯 **Key Achievements:**
- ✅ Successfully configured ADB environment and established device communication
- ✅ Installed and deployed AFLogical OSE APK to the target Android device
- ✅ Performed logical extraction of key user data (contacts, SMS/MMS, call logs)
- ✅ Successfully transferred extracted data from device to computer for analysis
- ✅ Analyzed extracted CSV files containing forensic evidence
- ✅ Completed proper cleanup and device disconnection procedures

**📊 Data Extraction Summary:**
- 👥 **Contacts:** Complete contact database with names, numbers, and details
- 💬 **SMS/MMS:** Text and multimedia message history with timestamps
- 📞 **Call Logs:** Incoming, outgoing, and missed call records
- 📅 **Metadata:** Device information and extraction timestamps
- 📁 **File Format:** CSV files for easy analysis and documentation

---

## � Notes

⚠️ **Legal Compliance:** Always ensure you have proper authorization before performing forensic extraction on any device. This tool should only be used for legitimate forensic investigations, academic research, or on devices you own.

🔒 **Data Security:** Handle extracted data with appropriate security measures. Forensic data may contain sensitive personal information that must be protected according to relevant privacy laws and regulations.

📱 **Device Compatibility:** AFLogical OSE works best with Android devices running older versions. Some newer Android versions may have enhanced security features that limit logical extraction capabilities.

🔍 **Further Analysis:** The extracted CSV data can be analyzed using various forensic tools and techniques:
- **Excel/Google Sheets** - Basic data analysis and visualization
- **Autopsy** - Advanced forensic analysis platform
- **Timeline Analysis** - Chronological event reconstruction
- **Data Correlation** - Cross-referencing multiple data sources

💡 **Best Practices:**
- Always create forensic images before extraction
- Document all procedures and findings thoroughly
- Maintain chain of custody for evidence
- Use write-blocking techniques when possible

---

**🔗 Related Tools:**
- [Autopsy](https://www.autopsy.com/) - Digital forensics platform
- [Volatility](https://www.volatilityfoundation.org/) - Memory forensics framework
- [SIFT Workstation](https://digital-forensics.sans.org/community/downloads) - Forensic analysis toolkit

---

*📅 Last Updated: October 2025*
*👨‍💻 Author: Digital Forensics Lab*

**� Download Required Files:**

1. **🔧 Android Platform Tools (ADB):**
   - Visit: [https://developer.android.com/tools/releases/platform-tools](https://developer.android.com/tools/releases/platform-tools)
   - Download `platform-tools-latest-windows.zip`

2. **📱 AFLogical OSE:**
   - **Primary Source:** [https://github.com/nowsecure/android-forensics](https://github.com/nowsecure/android-forensics)
   - **Alternative:** Search for "AFLogical OSE" on GitHub or forensic tool repositories
   - **Direct APK:** Some forensic distributions include pre-built APK files

3. **💻 Google USB Driver (Windows):**
   - Visit: [https://developer.android.com/studio/run/win-usb](https://developer.android.com/studio/run/win-usb)
   - Download `latest_usb_driver_windows.zip`

**�📋 Setup Instructions:**

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

3. **⚠️ Note on AFLogical OSE APK:**  
   If the AFLogical OSE download doesn't include the pre-built `AFLogical-OSE.apk`, you have several options:
   
   **Option A: Use Santoku Linux 0.5 (Your Downloaded File)**
   - **✅ You have:** `santoku_0.5` file downloaded
   - **📀 Create bootable media:** Use Rufus or similar tool to create bootable USB from ISO
   - **🖥️ Boot Santoku:** Boot your computer from USB or run in VirtualBox/VMware
   - **📂 Locate AFLogical OSE:** Navigate to `/usr/share/mobile-forensics/` or search for "aflogical"
   - **📱 Find APK:** Look for `AFLogical-OSE.apk` in the forensic tools directory
   - **💾 Copy to Windows:** Use USB drive or shared folder to transfer APK to `C:\DF\aflogical-ose\`

   **🚀 Quick Santoku 0.5 Setup Guide:**
   1. **📀 Create Bootable USB with Rufus:**
      - Download Rufus: [https://rufus.ie/](https://rufus.ie/)
      - Insert USB drive (8GB+ recommended)
      - **Launch Rufus and configure:**
        
        **📋 Rufus Configuration Settings:**
        ```
        Device: [Select your USB drive]
        Boot selection: [Click SELECT and choose santoku_0.5.iso]
        Image option: Standard Windows installation
        Partition scheme: MBR
        Target system: BIOS or UEFI
        File system: FAT32 (default)
        Cluster size: 4096 bytes (default)
        Volume label: SANTOKU
        ```
        
        **⚙️ Advanced Options (if needed):**
        - ✅ Check "Check device for bad blocks" (recommended)
        - ✅ Quick format (default)
        - ❌ Create extended label and icon files (uncheck)
        
      - **▶️ Click "START" to create bootable USB**
      - **⏳ Wait for completion (5-15 minutes depending on USB speed)**

   2. **💻 Boot into Santoku:**
      - Restart computer and boot from USB
      - Select "Live Boot" option (no installation needed)
      - Wait for desktop to load

   3. **🔍 Extract AFLogical OSE:**
      ```bash
      # Open terminal and search for AFLogical
      find /usr -name "*aflogical*" -type f 2>/dev/null
      find /home -name "*aflogical*" -type f 2>/dev/null
      ```

   4. **📁 Common Locations in Santoku 0.5:**
      - `/usr/share/santoku/mobile-forensics/`
      - `/opt/mobile-forensics/`
      - `/home/santoku/Desktop/Mobile-Forensics/`
   
   **Option B: Build from Source**
   - Install Android Studio with SDK
   - Clone the AFLogical OSE repository
   - Build the APK using Gradle: `./gradlew assembleDebug`
   
   **Option C: Alternative Downloads**
   - Search forensic tool repositories for pre-built APK
   - Check digital forensics communities and forums
   - Use DEFT Linux or other forensic distributions that include AFLogical OSE

<details>
<summary>📂 View Folder Structure</summary>
<br>
<p align="center">
  <img width="600" alt="DF folder structure with extracted files" src="https://github.com/omkarreddy652/digital-forensic-tools_overview/blob/main/images/placeholder.txt?raw=true" />
</p>
</details>

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
