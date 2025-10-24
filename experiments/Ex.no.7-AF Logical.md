# Ex.No.7 — AFLogical OSE: Android Logical Data Extraction

![AFLogical OSE](https://img.shields.io/badge/Tool-AFLogical_OSE-green)
![Platform](https://img.shields.io/badge/Platform-Android-lightgrey)
![Type](https://img.shields.io/badge/Extraction-Logical-blue)

---

## Table of Contents
- [Ex.No.7 — AFLogical OSE: Android Logical Data Extraction](#exno7--aflogical-ose-android-logical-data-extraction)
  - [Table of Contents](#table-of-contents)
  - [Aim](#aim)
  - [🛠️ Prerequisites \& Installation](#️-prerequisites--installation)
  - [Procedure](#procedure)
    - [Step 1: Prepare Environment \& Device](#step-1-prepare-environment--device)
    - [Step 2: Connect Android Device](#step-2-connect-android-device)
    - [Step 3: Install and Run AFLogical OSE](#step-3-install-and-run-aflogical-ose)
    - [Step 4: Transfer Extracted Data](#step-4-transfer-extracted-data)
    - [Step 5: Analyze Extracted Data](#step-5-analyze-extracted-data)
    - [Step 6: Clean Up](#step-6-clean-up)
  - [✅ Result](#-result)
  - [Notes 📌](#notes-)

---

## Aim
To use **AFLogical OSE (Open Source Edition)** to perform a logical extraction of data (like contacts, SMS messages, MMS messages, and call logs) from an Android device.

---

## 🛠️ Prerequisites & Installation

1. **Download AFLogical OSE:** Obtain the latest release `.apk` file from the official AFLogical OSE GitHub page.
2. **Install Java:** Ensure Java Development Kit (JDK) is installed on your computer, as ADB often requires it.
3. **Install Android Debug Bridge (ADB):**
   - Download ADB Platform Tools from the official Android Developers website.
   - Extract the tools to a known location (e.g., `C:\platform-tools`).
   - Add this location to your system's PATH environment variable so you can run `adb` commands from any terminal.
4. **Enable USB Debugging on Android Device:**
   - Go to `Settings` > `About Phone`.
   - Tap `Build Number` seven times until `Developer options` are enabled.
   - Go back to `Settings` > `System` > `Developer options`.
   - Enable `USB debugging`.

<details>
<summary>View USB Debugging Option 📱</summary>
<br>
<p align="center">
  <img width="400" alt="USB Debugging enabled in Android Developer Options" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

## Procedure

### Step 1: Prepare Environment & Device
- Ensure all prerequisites (AFLogical OSE `.apk`, Java, ADB, USB Debugging) are met before starting.
- Create a dedicated folder for your investigation, for example: `C:\Forensics_Lab\AFLogical_Data`.
- Verify that your computer can communicate with Android devices via ADB.

```bash
C:\Windows\System32> cd C:\platform-tools
```

📱 **Tip:** Make sure your Android device has Developer Options enabled and USB Debugging is turned on.

<details>
<summary>View Environment Setup 🛠️</summary>
<br>
<p align="center">
  <img width="800" alt="Command prompt navigated to platform-tools directory" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

### Step 2: Connect Android Device
- Connect the Android device to your computer using a USB cable.
- Open Command Prompt (`cmd.exe`) or Terminal on your computer.
- Verify ADB Connection by running the following command. You should see your device listed as 'device'.

```bash
C:\platform-tools> adb devices
```

📱 **Tip:** If prompted on the Android device, allow USB debugging access for your computer. You may need to check "Always allow from this computer".

<details>
<summary>View adb devices Output ✅</summary>
<br>
<p align="center">
  <img width="600" alt="adb devices command output showing connected device" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

### Step 3: Install and Run AFLogical OSE
- Use ADB to install the AFLogical OSE application onto the connected Android device.
- Replace `<path_to_apk>` with the actual path to your downloaded `.apk` file.
- Once installed, you'll need to launch the app and configure extraction settings.

```bash
C:\platform-tools> adb install "C:\Forensics_Lab\aflogical-ose.apk"
```

📲 **Tip:** After installation, open the AFLogical OSE app on the Android device and grant all necessary permissions for data access.

<details>
<summary>View AFLogical OSE Installation 📲</summary>
<br>
<p align="center">
  <img width="400" alt="AFLogical OSE app interface with data types selected" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

### Step 4: Transfer Extracted Data
- Use ADB to copy the `aflogical` folder (containing the `.csv` files) from the Android device to your computer.
- The app saves extracted data into `.csv` files in a folder named `aflogical` on the device's internal storage.
- Replace `/path/to/destination` with the path to your case folder.

```bash
C:\platform-tools> adb pull /sdcard/aflogical "C:\Forensics_Lab\AFLogical_Data"
```

💾 **Tip:** Navigate to the destination folder on your computer and confirm that the `aflogical` folder and its `.csv` files have been successfully copied.

<details>
<summary>View adb pull Command Execution 🖥️</summary>
<br>
<p align="center">
  <img width="800" alt="adb pull command transferring aflogical folder" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

### Step 5: Analyze Extracted Data
- Use software like Microsoft Excel, Google Sheets, LibreOffice Calc, or even a simple text editor to open the `.csv` files.
- The extracted files typically include `contacts.csv`, `sms.csv`, `calllog.csv`, and `mms.csv`.
- Review the data contents for relevant forensic information.

```bash
C:\platform-tools> explorer "C:\Forensics_Lab\AFLogical_Data\aflogical"
```

📊 **Tip:** Examine the contents for relevant information like contact details, message contents, call timestamps, and durations. Document any significant findings.

<details>
<summary>View Sample CSV Data 📊</summary>
<br>
<p align="center">
  <img width="800" alt="Sample CSV data opened in spreadsheet software" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

### Step 6: Clean Up
- Remove the AFLogical OSE app from the Android device using ADB for security purposes.
- Disable USB debugging on the device to maintain security.
- Safely disconnect the USB cable and document the extraction process.

```bash
C:\platform-tools> adb uninstall com.viaforensics.android.aflogical
```

🧹 **Tip:** For security, go back into Developer options on the Android device and disable USB debugging after completing the extraction.

<details>
<summary>View Cleanup Process 🧹</summary>
<br>
<p align="center">
  <img width="600" alt="AFLogical OSE app being uninstalled via ADB" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</p>
</details>

---

## ✅ Result
By following these steps, we successfully used AFLogical OSE to perform a logical extraction of data from the connected Android device. We were able to:

- Prepare the environment and enable USB debugging on the Android device.
- Connect the device and verify ADB communication.
- Install AFLogical OSE app and configure data extraction settings.
- Extract user data (Contacts, SMS, MMS, Call Logs) to CSV format.
- Transfer the extracted data to the analysis computer using ADB.
- Analyze the extracted data using standard spreadsheet software.
- Clean up by removing the app and disabling USB debugging.

All extracted data files are now stored in the `C:\Forensics_Lab\AFLogical_Data` case folder, ready for forensic analysis and reporting.

---

## Notes 📌

⚠️ **Legality & Permissions:** Ensure you have the legal authority and necessary permissions before extracting data from any device.

✅ **Logical vs. Physical:** AFLogical OSE performs a logical extraction, accessing data through the operating system's APIs. This is less comprehensive than a physical extraction but doesn't require rooting.

📲 **Device Compatibility:** AFLogical OSE's success may vary depending on the Android version and device manufacturer. Some permissions may be restricted on newer Android versions.

💾 **Data Location:** The extracted data folder is typically `/sdcard/aflogical`, but this might differ slightly on some devices depending on the Android version and manufacturer customizations.
