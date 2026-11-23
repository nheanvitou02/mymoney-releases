# Privacy Policy — MyMoney (លុយខ្ញុំ)

**Effective Date:** November 18, 2026  
**Application:** MyMoney (លុយខ្ញុំ)  
**Package:** `com.mymoney.app`  

---

## 1. Introduction & Core Philosophy

**MyMoney (លុយខ្ញុំ)** is designed from the ground up as a **100% Local-First, Offline-Only** personal finance application. We believe that your personal financial records—income, daily expenses, savings targets, and net balances—belong exclusively to you.

This Privacy Policy explains how MyMoney handles data on your mobile device.

> [!IMPORTANT]
> **Notice of Scope:** This Privacy Policy accurately reflects the actual technical implementation and data architecture of MyMoney version 1.0.1. It is provided for complete transparency and has not undergone formal legal review.

---

## 2. Information Handled by the Application

All data entered into MyMoney is stored strictly on your local device. The application processes:

- **Financial Transactions:** Transaction amounts, entered currencies (USD cents or KHR riels), selected categories, dates, and optional user notes.
- **Categories:** System-default category preferences (names, icons, colors) and any user-customized categories.
- **Savings Goals:** Goal titles, target amounts, selected currencies, deadlines, contribution records, and archive statuses.
- **User Preferences:** Preferred interface language (`km` or `en`), display currency (`USD` or `KHR`), custom exchange rate (e.g. 4,100 KHR per 1 USD), KHR rounding mode, theme preference (`LIGHT`, `DARK`, or `SYSTEM`), and onboarding completion state.

---

## 3. Where and How Data is Stored

- **100% On-Device Storage:** All financial records and settings are stored locally in a relational SQLite database (`mymoney.db`) located within the operating system's private application sandbox.
- **No Cloud Accounts or Servers:** MyMoney does not operate user accounts, cloud databases, synchronization servers, or remote backends.
- **Zero Network Exfiltration:** The application never transmits your financial data, transaction history, or personal identifiers over the internet.

---

## 4. Third-Party Analytics, Tracking, and Advertising

- **Zero Analytics SDKs:** MyMoney contains no telemetry frameworks, behavioral analytics tools (such as Google Analytics or Firebase), or crash-reporting trackers.
- **Zero Advertising Identifiers:** The application does not collect, access, or share Google Advertising IDs (AAID) or device fingerprinting tokens.
- **Zero Third-Party Sharing:** No financial data is ever sold, transferred, or shared with third parties, financial institutions, or external APIs.

---

## 5. Device Permissions

MyMoney requests **zero dangerous Android runtime permissions** (`"permissions": []` in application manifest):

- **No Camera or Microphone**
- **No Location Tracking (GPS or Network)**
- **No Contacts or Address Book**
- **No SMS or Phone State**
- **No Background Sync**

### File Storage Access & Sharing
When you voluntarily choose to use the **Data Backup** (JSON export/import) or **CSV Transaction Export** features in Settings:
- Files are generated in the app's internal cache directory.
- The standard Android system share sheet (`expo-sharing` / `expo-document-picker`) is invoked so you can save the export file to your device storage, email it to yourself, or store it in your personal cloud storage (e.g., Google Drive).
- MyMoney accesses files only when explicitly selected by you through the system document picker.

---

## 6. Data Retention, Portability, and Deletion

- **You Own Your Data:** You can export a complete, portable copy of your entire SQLite database at any time (**Settings > Export Data Backup (JSON)**).
- **Data Deletion:** You can permanently erase all transactions, goals, and customized settings at any time using the double-confirmation **Reset Database** option in Settings.
- **App Uninstallation:** Uninstalling MyMoney from your Android device immediately and permanently deletes the local SQLite database and all associated application sandbox data.

---

## 7. Support & Security Inquiries

If you have questions regarding this Privacy Policy or wish to report a security observation, please open an issue in our official release repository:  
**[https://github.com/nheanvitou02/mymoney-releases/issues](https://github.com/nheanvitou02/mymoney-releases/issues)**
