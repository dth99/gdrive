# gdrive

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

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
  Graceful handling of network interruptions and API errors, with clear console logging.

---

## 📸 Screenshots

![Introduction](https://github.com/dth99/gdrive/blob/main/drive-intro.png)

![Upload Step 1](https://github.com/dth99/gdrive/blob/main/p1.png)  
![Upload Step 2](https://github.com/dth99/gdrive/blob/main/p2.png)  
![Upload Step 3](https://github.com/dth99/gdrive/blob/main/p3.png)  
![Upload Step 4](https://github.com/dth99/gdrive/blob/main/p4.png)  
![Upload Step 5](https://github.com/dth99/gdrive/blob/main/p5.png)

---

## 🛠️ Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/dth99/gdrive.git
   cd gdrive
```

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
   * Create/select a project and enable the **Google Drive API**.
   * Create OAuth2 credentials (Desktop app), download `credentials.json`, and place it in the project root.

---

## ⚙️ Configuration

* **SCOPES**
  By default the script uses:

  ```python
  SCOPES = ["https://www.googleapis.com/auth/drive"]
  ```

  to grant full Drive access.
* **Local folder to back up**
  Edit the `backupfiles/` path in `backup.py` if you wish to sync a different directory.

---

## 📂 Usage

Run the script to perform the initial OAuth flow and upload:

```bash
python backup.py
```

Typical console output:

```
Token not found—launching browser for authentication...
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
2. Add a line to run hourly:

   ```cron
   0 * * * * /path/to/venv/bin/python /path/to/gdrive/backup.py >> /path/to/gdrive/logs/backup.log 2>&1
   ```

### Windows (Task Scheduler)

1. Open Task Scheduler → Create Basic Task.
2. Set a trigger (e.g., daily/hourly).
3. Action: **Start a program**

   * Program/script: `C:\path\to\venv\Scripts\python.exe`
   * Add arguments: `"C:\path\to\gdrive\backup.py"`

---

## 📦 Dependencies

* `google-auth`
* `google-auth-oauthlib`
* `google-api-python-client`

Install with:

```bash
pip install google-auth google-auth-oauthlib google-api-python-client
```

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repo
2. Create a branch (`git checkout -b feature/YourFeature`)
3. Commit changes (`git commit -m "Add YourFeature"`)
4. Push (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License—see the [LICENSE](LICENSE) file for details.

---

## 🙋‍♂️ Contact

* **LinkedIn:** [deepakkumar2o](https://www.linkedin.com/in/deepakkumar2o/)
* **Email:** [deep99.official@gmail.com](mailto:deep99.official@gmail.com)

Feel free to connect or send any questions!\`\`\`
