# ReNotePad Privacy Policy

**Last updated:** July 28, 2026
**Applies to:** ReNotePad for Android (package `com.renotepad.app`)

## 1. Introduction

This privacy policy describes how ReNotePad ("the app", "we") handles information when you use the application. ReNotePad is a general-purpose text and code editor that runs entirely on the user's device.

Our design principle is simple: **the app doesn't need your data to work, so it doesn't collect it**. There are no user accounts, no servers we operate, and no cloud infrastructure associated with ReNotePad.

By installing and using ReNotePad, you agree to the practices described in this document.

## 2. Data controller

This app is developed and published by an independent developer. For any privacy-related inquiry, the point of contact is listed in Section 11.

## 3. Executive summary

| Question | Answer |
|---|---|
| Does the app connect to the internet? | No. It does not request the `INTERNET` permission and cannot perform network communication. |
| Is personal data collected? | No. |
| Are cookies, analytics SDKs, or advertising used? | No. |
| Does my file content ever leave the device? | No, unless you explicitly share it with another app yourself. |
| Is there a user account? | No. |
| Is data sold or shared with third parties? | No, because no data is collected to share in the first place. |

## 4. Data categories and how they are handled

### 4.1 Your file content
ReNotePad accesses a file's content only when you explicitly open it through the operating system's document picker (Storage Access Framework, "SAF"). This mechanism is managed by Android, not by the app: the operating system grants access only to the specific document you select, and ReNotePad cannot list, index, or access any other file on your storage.

Content is processed only in the device's memory while you edit, and written back to the same document (or another one you choose via "Save as") when you save. At no point is the content transmitted off the device, uploaded to a server, or logged to any telemetry system, because no such system exists in the app.

### 4.2 Recent files list
For your convenience, the app keeps a local list of up to 10 recently opened files. For each entry it stores:

- The document reference (URI) granted by the system when access was allowed.
- The file name.
- The timestamp it was opened.

This data is stored in `SharedPreferences`, a private storage mechanism protected by Android's app sandboxing: no other app can read it. It is not synced to any server, and it is not included in any cloud backup unless you have Android's automatic backup feature enabled (`android:allowBackup`), in which case Android may include it in your private backup tied to your Google account — entirely under Google's and your own control, not ReNotePad's.

You can clear this list at any time from within the app, and it is automatically removed if you uninstall ReNotePad.

### 4.3 Sharing files with other apps
If you use the "Share" feature, ReNotePad hands a read-only copy of the active file to the destination app you choose, via a standard Android `FileProvider` with a temporary, single-use access grant. ReNotePad does not inspect the content of that transfer and keeps no record of which app or person the file was shared with. The privacy policy of the receiving app (e.g., your email client) applies from that point forward.

### 4.4 Data the app does NOT collect
For clarity, ReNotePad explicitly does not collect, process, or transmit:

- Device identifiers (IMEI, Android ID, advertising ID, etc.)
- Location data
- Contacts, calendar, or other personal information from the system
- Biometric data
- Payment information
- Usage statistics, interaction events, or crash logs (no analytics or crash-reporting SDK is integrated)
- IP address or any other network data (there is no internet connection)

## 5. App permissions

| Permission | Type | Purpose | Notes |
|---|---|---|---|
| Document access via the system picker (Storage Access Framework) | No runtime permission required | Open and save the files you explicitly choose | Access is granted per document by the user and can be revoked at any time from Android settings |

ReNotePad does not declare broad storage permissions (`READ_EXTERNAL_STORAGE`, `WRITE_EXTERNAL_STORAGE`), media access (`READ_MEDIA_IMAGES`), camera, microphone, contacts, location, or any other dangerous or sensitive permission.

## 6. Data sharing and disclosure to third parties

ReNotePad does not share data with third parties because it does not collect data in the first place. Specifically:

- No integration with advertising networks.
- No analytics SDKs (Firebase Analytics, Google Analytics, Mixpanel, etc.).
- No crash-reporting services (Crashlytics or otherwise).
- No third-party services of any kind embedded in the app.

## 7. Security

Because ReNotePad never transmits data off the device, the risk surface is limited to the device itself. The app benefits from Android's standard sandboxing: its private data (`SharedPreferences`) is only accessible to the app itself, and access to your documents is always mediated by permissions the operating system controls, not the app.

We recommend keeping your operating system up to date and using your device's own security features (screen lock, storage encryption) as an additional layer of protection for your files.

## 8. Data retention

- **File content:** no copy is retained anywhere outside the file you manage in your own storage.
- **Recent files list:** retained until you manually clear it or uninstall the app.

## 9. Your rights and control

Because no personal information is collected on any server, there is no data for us to provide, correct, or delete under regulations such as the GDPR or CCPA — all relevant information (your files and your recent files list) is already under your direct control, on your own device. You can:

- Revoke access to any document from Android's permission settings.
- Clear the recent files list from within the app.
- Remove all data associated with the app by uninstalling it.

## 10. Children's privacy

ReNotePad is not specifically directed at children and does not include any features designed to collect information from any user, including minors. Anyone can use the app with the same assurance that no personal information is collected.

## 11. Changes to this policy

We may update this policy to reflect changes to the app or for legal reasons. Any change will be posted on this same page with a new "Last updated" date. We encourage you to review it periodically.

## 12. Contact

If you have questions, concerns, or requests related to this Privacy Policy, please open an issue in the ReNotePad GitHub repository.
