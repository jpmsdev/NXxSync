# NXxSync

Homebrew written in C++ to sync files.

The app performs **WebDAV** sync/transfers using a job queue (backup/restore/sync) and provides UI screens to manage **Clients** and **Nodes**.


## Usage
- Copy `build/NXxSync.nro` to `switch/` on the SD card.


## Features

- **Home**: shortcuts to Clients, Nodes, and Transfer.
- **Clients**: server configuration.
- **Nodes**: path configuration (Local Path, Remote Path, Backup Path) + actions:
  - **Backup**: uploads files to **Backup Path** and, when finished, publishes to **Remote Path**.
  - **Restore**: downloads from **Remote Path** to **Local Path**.
  - **Sync**: uploads to **Backup Path**, restores from **Remote Path**, then publishes the new backup to **Remote Path**.
- **Transfer**: runs the queue (Play/Pause), Retry All, Cancel All, footer with progress/ETA and current file name (shows only the tail of the path).
- **Header**: **Sleep on done?** toggle to enter system sleep when transfers finish (uses `appletRequestToSleep`; on failure or old firmware, exits the app instead).
