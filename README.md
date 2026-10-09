# 🎙️ Python Voice Assistant

**A smart, voice-controlled desktop assistant built with Python.**

Control Windows applications, open websites, search the web, check the weather, manage notes and tasks, set reminders, and interact with an AI service using natural language.

## ✨ Features

* 🎤 **Speech Recognition** — Convert spoken commands into text.
* 🔊 **Text-to-Speech** — Receive spoken responses from the assistant.
* 🖥️ **Windows Automation** — Open applications such as Chrome, Notepad, Calculator, File Explorer, and VS Code.
* 🌐 **Web Automation** — Open Google, YouTube, GitHub, Gmail, and ChatGPT.
* 🔎 **Web Search** — Search Google and YouTube using voice commands.
* 🌦️ **Weather Updates** — Retrieve current weather using the OpenWeather API.
* ⏰ **Time, Date & Reminders** — Get the current time and date and schedule basic reminders or alarms.
* 📝 **Notes & Tasks** — Save and retrieve personal notes and to-do tasks.
* 🤖 **AI Conversations** — Answer general questions using the OpenAI API.
* 🗄️ **Data Persistence** — JSON-based storage in the initial version, with SQLite integration planned or in progress.

## 🛠️ Tech Stack

| Technology        | Purpose                    |
| ----------------- | -------------------------- |
| Python            | Core programming language  |
| SpeechRecognition | Speech-to-text             |
| PyAudio           | Microphone input           |
| pyttsx3           | Text-to-speech             |
| OpenWeather API   | Weather information        |
| OpenAI API        | AI-powered conversations   |
| SQLite            | Local database and history |
| python-dotenv     | Environment configuration  |
| Git & GitHub      | Version control            |

## 📁 Project Structure

```text
PythonVoiceAssistant/
├── app/
│   ├── core/
│   │   └── config.py
│   ├── voice/
│   │   ├── listener.py
│   │   └── speaker.py
│   ├── commands/
│   │   ├── router.py
│   │   ├── windows.py
│   │   ├── reminder.py
│   │   ├── weather.py
│   │   ├── notes.py
│   │   └── ai.py
│   ├── database/
│   │   └── db.py
│   ├── utils/
│   │   └── logger.py
│   └── main.py
├── tests/
├── .env.example
├── .gitignore
├── requirements.txt
├── README.md
└── assistant.db  # Local runtime database; do not commit
```

*The structure may evolve as development progresses.*

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/PythonVoiceAssistant.git
cd PythonVoiceAssistant
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Create a virtual environment

**Windows PowerShell:**

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```powershell
python -m pip install -r requirements.txt
```

If needed, install the main packages individually:

```powershell
python -m pip install python-dotenv requests openai pyttsx3 SpeechRecognition PyAudio
```

### 4. Configure environment variables

Create a `.env` file in the project root:

```env
APP_NAME=Python Voice Assistant
APP_VERSION=1.0.0
OPENWEATHER_API_KEY=your_openweather_api_key
OPENAI_API_KEY=your_openai_api_key
```

Obtain API credentials from:

* [OpenWeather](https://openweathermap.org/api)
* [OpenAI API Platform](https://platform.openai.com/)

API usage may require separate billing or credits.

### 5. Run the assistant

```powershell
python -m app.main
```

Allow microphone access when prompted by Windows.

## 🎤 Example Voice Commands

| Command                     | Action                |
| --------------------------- | --------------------- |
| `Hello`                     | Greet the assistant   |
| `Open Chrome`               | Launch Chrome         |
| `Open YouTube`              | Open YouTube          |
| `Search Python FastAPI`     | Search Google         |
| `Weather in Goa`            | Get current weather   |
| `What time is it?`          | Tell the current time |
| `What is today's date?`     | Tell the current date |
| `Add note learn FastAPI`    | Save a note           |
| `Show my notes`             | Read saved notes      |
| `Add task complete project` | Add a to-do task      |
| `Show my tasks`             | Read saved tasks      |
| `Tell me what Python is`    | Ask the AI service    |
| `Exit`                      | Stop the assistant    |

*The exact supported phrases depend on the current command router implementation.*

## 🏗️ Architecture

```text
Microphone
    ↓
Speech Recognition
    ↓
Command Router
    ├── Windows Controller
    ├── Weather Service
    ├── Notes & Tasks
    ├── Reminder Manager
    └── AI Service
            ↓
       Voice Speaker
```

External APIs handle weather and AI requests, while local modules handle desktop actions and personal productivity features.

## 🔐 Security

* Store API keys in `.env`.
* Never commit secrets or personal database files.
* Keep `.env`, `venv/`, `__pycache__/`, and local databases in `.gitignore`.
* Avoid logging API keys or sensitive personal information.



## 🧪 Testing

Automated tests will be added with `pytest`. External API requests should be mocked in unit tests to avoid unnecessary API usage.

## 🎯 Project Goal

Build a modular Python desktop assistant that combines voice interaction, Windows automation, API integration, local data management, and AI capabilities while applying practical software engineering principles.

## 👨‍💻 Author

**Chaitanya Modi**

Python Backend Developer

## 📄 License

This project is intended for learning and portfolio development. Add an MIT License if you want to distribute it under that license.

