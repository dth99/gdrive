````markdown
# CloudDriveSync

A lightweight, cross‑platform Python utility that turns any local folder into your personal Google Drive “Dropbox” clone—perfect for automated backups, versioning, and seamless cloud storage.

---

## 🚀 Features

- **OAuth2 Authentication**  
  Securely authenticate via Google’s OAuth2 flow; tokens are stored in `token.json` and automatically refreshed.
- **Idempotent Folder Management**  
  Looks up (or creates) a Drive folder named `BackupFoler2022` and reuses it on every run—no duplicate folders.
- **Chunked File Uploads**  
  Streams large files in chunks with `MediaFileUpload` for reliable, resumable transfers.
- **Cross‑Platform Support**  
  Pure Python (3.6+) solution with no OS‑specific binaries—runs on Windows, macOS, and Linux.
- **Scheduler‑Ready**  
  Integrates seamlessly with `cron` (Linux/macOS) or Task Scheduler (Windows) for hands‑off periodic syncs.
- **Error Handling**  
  Graceful handling of `HttpError` and network interruptions, with clear console logging.

---

## 📸 Screenshots

![Auth Flow Screenshot](./screenshots/auth-flow.png)  
*OAuth consent screen and token storage confirmation.*

![Backup in Action](./screenshots/backup-running.png)  
*Uploading multiple files to Google Drive in one go.*

---

## 🛠️ Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/CloudDriveSync.git
   cd CloudDriveSync
````

2. **Create & activate a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # macOS/Linux
   venv\Scripts\activate      # Windows
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up Google API credentials**

   * Go to the [Google Cloud Console](https://console.cloud.google.com/).
   * Create a new project or select an existing one.
   * Enable the **Google Drive API**.
   * Create OAuth2 credentials (Desktop app) and download `credentials.json` into the project root.

---

## ⚙️ Configuration

* **SCOPES**
  By default, the script uses `["https://www.googleapis.com/auth/drive"]` to grant full Drive access.
* **Local folder to back up**
  Change the `backupfiles/` directory if you wish to sync a different local path.

---

## 📂 Usage

Run the script once to complete the initial OAuth flow and token storage:

```bash
python backup.py
```

You should see console output like:

```
Token file not found—launching browser for authentication...
Authenticated! Token saved to token.json.
Backup folder found/created with ID: 1AbcD2EfGh...
Backing up file: project1.py
Backing up file: notes.txt
…
```

---

## ⏰ Scheduling

### Linux/macOS (cron)

1. Open your crontab:

   ```bash
   crontab -e
   ```
2. Add a line to run every hour:

   ```cron
   0 * * * * /path/to/venv/bin/python /path/to/CloudDriveSync/backup.py >> /path/to/CloudDriveSync/logs/backup.log 2>&1
   ```

### Windows (Task Scheduler)

1. Open Task Scheduler and create a new Basic Task.
2. Set the trigger (e.g., daily/hourly).
3. For the Action, select **Start a program** and point to:

   ```
   Program/script: C:\path\to\venv\Scripts\python.exe
   Add arguments: "C:\path\to\CloudDriveSync\backup.py"
   ```

---

## 📦 Dependencies

* `google-auth`
* `google-auth-oauthlib`
* `google-api-python-client`
* (Built‑in Python libraries: `os`, `sys`, etc.)

Install them via:

```bash
pip install google-auth google-auth-oauthlib google-api-python-client
```

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork this repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m "Add YourFeature"`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request describing your enhancements.

---

## 📝 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for more information.

---

## 🙋‍♂️ Author

**Your Name** — [your.email@example.com](mailto:your.email@example.com)
Follow me on [LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)

```
```



# gdrive

![dth99](https://github.com/dth99/gdrive/blob/main/drive-intro.png)

![dth99](https://github.com/dth99/gdrive/blob/main/p1.png)
![dth99](https://github.com/dth99/gdrive/blob/main/p2.png)
![dth99](https://github.com/dth99/gdrive/blob/main/p3.png)
![dth99](https://github.com/dth99/gdrive/blob/main/p4.png)
![dth99](https://github.com/dth99/gdrive/blob/main/p5.png)
