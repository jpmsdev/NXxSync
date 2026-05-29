# NXxSync

A free multi-protocol file synchronization and backup utility written in C++ for libnx-compatible environments.

**NXxSync** allows you to seamlessly back up, restore, and synchronize local directories with remote servers directly from your device. The application operates using an asynchronous job queue, ensuring stable network transfers without freezing the user interface.

## 🚀 Features

* **Multi-Protocol Architecture:** Engine designed to support multiple network protocols. 
  * 🟢 **WebDAV:** Supported.
  * 🟢 **MEGA:** Supported on version 1.2.0. Limit 1 thread.
  
  * 🟡 **Future Protocols:** Planned support for FTP, SFTP, and SMB/Samba.
* **Smart Job Queue:** Robust background transfer manager with Play, Pause, Retry All, and Cancel All capabilities.
* **Dynamic Node Management:** Configure source and destination mappings with three flexible actions:
  * **Backup:** Uploads local files to your secure Backup Path and publishes to the Remote Path.
  * **Restore:** Downloads data from the Remote Path directly back to your Local Path.
  * **Sync:** Performs a safe bi-directional cycle (Uploads current state to Backup Path, restores updates from Remote Path, and refreshes the remote repository).
* **Power Management:** Includes a "Sleep on Done" toggle that automatically puts the device into system sleep (`appletRequestToSleep`) once all queue tasks are successfully completed.
* **UI/UX Optimized:** Clean interface featuring real-time progress bars, ETA calculation, and dynamic path tail display.

## 📂 Installation

1. Download the latest `NXxSync.nro` from the [Releases](../../releases) section.
2. Copy the `.nro` file into the `/switch/` directory on your SD card.
3. Launch via your preferred homebrew menu.

## 🛠️ Configuration

* **Clients:** Set up your remote server addresses, ports, and credentials. 
  * _Note for WebDAV: While the "New Client" template comes pre-configured for Koofr WebDAV for quick testing, NXxSync works with any standard WebDAV server (Nextcloud, OwnCloud, NAS, etc.)._
  * _Note for MEGA: Authentication is handled locally and securely. Input your credentials to establish a direct encrypted session with MEGA servers._
* **Nodes:** Define your local-to-remote folder pairings and assign their respective backup behaviors.

---

## ⚖️ Disclaimer & Risk Notice

**CRITICAL NOTICE:** Data synchronization is inherently subject to external variables. Due to a variety of factors—including but not limited to network instability, internet disconnection, power loss, device sleep states, remote server downtime, or API changes—**data corruption or permanent data loss may occur.** 

By using this software, you acknowledge and agree that:
* **You are solely responsible** for manually verifying that your files have been correctly and completely synchronized.
* **You should always maintain secondary backups** of your most critical data (such as important game saves) before running synchronization tasks.
* The developer(s) of NXxSync cannot be held liable for any data loss, corruption, or hardware malfunction resulting from the use of this utility.

This is an independent utility developed strictly for personal data backup, synchronization, and system interoperability. It is not affiliated, associated, authorized, endorsed by, or in any way officially connected with any console manufacturer or its subsidiaries. 

### Third-Party Service Disclaimer (MEGA)
NXxSync is a third-party free application and is **NOT** affiliated, associated, authorized, endorsed by, or in any way officially connected with MEGA Limited or any of its subsidiaries. The name "MEGA", as well as related marks, emblems, and images, are registered trademarks of their respective owners. Use of the MEGA integration is at your own discretion and must comply with MEGA's Terms of Service.

Provided "as-is" without warranties of any kind. Use at your own risk.

<!-- REMOVE OR KEEP THIS SECTION IF YOU DID NOT USE THE OFFICIAL MEGA SDK -->
## 📜 License & Acknowledgments

<!-- This project is licensed under the [Your License, e.g., MIT License]. -->

* This software may include code or libraries from the **MEGA SDK**, Copyright (c) 2012-2026 Mega Limited, used under the BSD 2-Clause License.
