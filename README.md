# 🎵 YouTube Mashup Generator

> **Create custom audio mashups from YouTube videos with a single click!**

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0+-green?style=flat-square&logo=flask)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

[🌐 Live Demo](#live-demo) • [📖 Documentation](#documentation) • [🚀 Quick Start](#quick-start) • [⚙️ Setup](#setup)

</div>

---

## 📋 Overview

A comprehensive mashup generation system that downloads multiple YouTube songs from your favorite artist, extracts audio, trims segments, and merges them into a single cohesive mashup file. Available as both a **Command-Line Tool** and a **Web Application** with email delivery.

**Project By:** Manav | **Roll No:** 102303990

---

## ✨ Features

### 🖥️ **Command-Line Tool** (`102303990.py`)
- ⬇️ Download N videos from YouTube automatically
- 🎵 Convert video files to MP3 format
- ✂️ Trim first X seconds from each audio file
- 🔗 Merge all trimmed segments into single file
- ✅ Input validation with helpful error messages
- 🛡️ Robust exception handling

### 🌐 **Web Application** (`app.py`)
- 🎯 User-friendly web interface
- 📧 Automated email delivery with ZIP attachment
- 💾 Direct browser download option
- 🔐 Email validation and input sanitization
- ⚡ Concurrent processing with unique job IDs
- 📦 Automatic cleanup of temporary files

---

## 🎯 How It Works

```
YouTube Videos
     ⬇️
Download & Extract Audio
     ⬇️
Convert to MP3 Format
     ⬇️
Trim First X Seconds
     ⬇️
Merge All Segments
     ⬇️
Create ZIP Package
     ⬇️
Send via Email / Download
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- FFmpeg installed on system
- Internet connection

### Installation

```bash
# Clone the repository
git clone https://github.com/manav-bhullar/mashup-main.git
cd mashup-main

# Install Python dependencies
pip install -r requirements.txt

# Install FFmpeg
# macOS
brew install ffmpeg

# Ubuntu/Debian
sudo apt-get install ffmpeg

# Windows
choco install ffmpeg
```

### 1️⃣ Command-Line Usage

```bash
python 102303990.py <SingerName> <NumberOfVideos> <Duration> <OutputFile>
```

**Example:**
```bash
python 102303990.py "Arijit Singh" 15 30 arijit_mashup.mp3
```

**Input Constraints:**
| Parameter | Minimum | Format |
|-----------|---------|--------|
| Number of Videos | 10 | Integer |
| Duration (seconds) | 20 | Integer |
| Output File | - | Must end with `.mp3` |

**Error Handling:**
- Invalid parameter count → Usage instructions
- Non-integer videos/duration → Error message
- File constraints violated → Validation error
- Download failures → Exception handling with rollback

---

### 2️⃣ Web Application Setup

#### Configuration

Create a `.env` file in project root:

```env
SENDER_EMAIL=your-email@gmail.com
SENDER_PASSWORD=your-app-password
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
PORT=5000
```

**📌 Gmail Setup:**
1. Enable 2-Factor Authentication
2. Generate [App Password](https://myaccount.google.com/apppasswords)
3. Use App Password (not your actual Gmail password)

#### Run Web Server

```bash
python app.py
```

**Access at:** `http://localhost:5000`

**For Production:**
```bash
python app.py  # Server runs on port from .env or default 5000
```

---

## 📂 Project Structure

```
mashup-main/
├── 102303990.py           # CLI mashup generator
├── app.py                  # Flask web application
├── requirements.txt        # Python dependencies
├── Procfile               # Render deployment config
├── .env                   # Environment variables (create this)
├── README.md              # This file
└── templates/
    ├── index.html         # Web form
    └── result.html        # Results page
```

---

## 🔧 Technology Stack

| Component | Technology |
|-----------|-----------|
| **Backend** | Python 3.8+ |
| **Web Framework** | Flask 2.0+ |
| **Video Download** | yt-dlp |
| **Audio Processing** | pydub, FFmpeg |
| **Email Service** | SMTP |
| **Cloud Hosting** | Render |

---

## 📊 Web Application Workflow

```
User Input (Singer, Videos, Duration, Email)
         ⬇️
Input Validation
         ⬇️
Create Unique Job ID
         ⬇️
Download Videos from YouTube
         ⬇️
Convert to MP3
         ⬇️
Cut Audio Segments
         ⬇️
Merge into Single File
         ⬇️
Create ZIP Package
         ⬇️
Send Email + Return Download Link
         ⬇️
Cleanup Temporary Files
```

---

## 🌐 Live Demo

**Production URL:** https://mashup-xwsv.onrender.com/

Try it live with your favorite artist! No installation required.

---

## 📦 Dependencies

```
Flask==2.3.0
yt-dlp==2023.0.0
pydub==0.25.1
python-dotenv==1.0.0
```

Install all at once:
```bash
pip install -r requirements.txt
```

---

## ⚠️ Important Notes

- **CLI minimum videos:** 10 (Web minimum: 2)
- **Minimum duration:** 20 seconds
- **Output format:** MP3 only
- **Internet required:** For YouTube downloads
- **FFmpeg required:** For audio processing
- **Temp files:** Automatically cleaned after processing
- **Processing time:** Depends on number of videos and duration

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| FFmpeg not found | Install FFmpeg and add to PATH |
| yt-dlp errors | Update: `pip install --upgrade yt-dlp` |
| Email not sending | Check `.env` credentials and 2FA/App Password |
| Video download fails | Check internet connection and YouTube availability |
| Audio conversion error | Ensure FFmpeg is properly installed |

---

## 📝 License

This project is open source and available under the MIT License.

---

## 👨‍💻 Author

**Manav**  
Roll No: **102303990**

---

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

---

<div align="center">

**Made with ❤️ by Manav**

[⬆ Back to top](#-youtube-mashup-generator)

</div>
