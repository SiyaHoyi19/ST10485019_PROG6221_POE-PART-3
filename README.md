# CyberBot — Cybersecurity Awareness Chatbot

A WPF desktop application built in C# (.NET 8.0) that educates users about cybersecurity through an interactive chatbot, task assistant, quiz mini-game, and activity log.

---

## Student Information

- **Name:** Siyahluma Hoyi
- **Student Number:** ST10485019
- **Module:** PROG6221 — Part 3

---

##  Features

### Part 1 — Core Chatbot
- Voice greeting plays on launch (`greeting.wav`)
- ASCII art displayed in the GUI header
- Bot asks for your name and uses it throughout the conversation
- Recognises 12+ cybersecurity keywords: `password`, `phishing`, `privacy`, `scam`, `malware`, `vpn`, `firewall`, `2fa`, `ransomware`, `social engineering`, `safe browsing`and `hacking`
- Multiple random responses per keyword
- Sentiment detection — detects `worried`, `curious`, `frustrated`, `happy` tones and responds empathetically
- Follow-up phrases like `tell me more` continue the current topic
- Memory store persists user name and favourite topic across the session

### Part 2 — Task Assistant & Quiz
- Task assistant panel with add, view, complete, and delete functionality
- Tasks saved to and loaded from `tasks.json` automatically
- `tasks.json` is auto-created when the first task is added — no manual setup needed
- Reminder field captured and stored with each task
- Cybersecurity quiz with 12 questions covering phishing, passwords, safe browsing, social engineering, 2FA, malware, and privacy
- Quiz shows one question at a time with immediate feedback and explanation
- Final score and motivational message displayed at the end

### Part 3 — NLP, Activity Log & Integration
- NLP detects task, quiz, and log intents from varied phrasings (e.g. "I need to enable 2FA", "test my knowledge", "what have you done for me?")
- Activity log records tasks, reminders, quiz starts, completions, and keyword matches with timestamps
- Log shows last 10 entries by default; `show more` displays full history
- All three parts work together seamlessly in one WPF application

---

## Prerequisites

- **Visual Studio 2022** (Community or higher)
- **.NET 8.0 SDK**
- **Newtonsoft.Json NuGet package** (see setup below)

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/SiyaHoyi19/ST10485019_PROG6221.git
cd ST10485019_PROG6221
```

### 2. Open in Visual Studio

- Open `CybersecurityChatbot.sln` in Visual Studio 2022

### 3. Install Newtonsoft.Json NuGet Package

The project requires `Newtonsoft.Json` for JSON task storage:

1. In Visual Studio, go to **Tools → NuGet Package Manager → Manage NuGet Packages for Solution**
2. Click the **Browse** tab
3. Search for `Newtonsoft.Json`
4. Select the package and click **Install**
5. Accept any license prompts

Alternatively, run this in the **Package Manager Console**:

```powershell
Install-Package Newtonsoft.Json
```

### 4. Add the Greeting Sound File

- Place your `greeting.wav` file in the **project root folder** (same folder as `CybersecurityChatbot.csproj`)
- In Solution Explorer, right-click `greeting.wav` → **Properties**
- Set **Copy to Output Directory** to **Copy if newer**

> ⚠️ Without `greeting.wav`, the app still runs — the voice greeting will simply be skipped silently.

### 5. Run the Project

- Press **F5** or click the green **Run** button in Visual Studio
- The app launches with a voice greeting, ASCII art header, and prompts you for your name

> 📝 `tasks.json` is created automatically when you add your first task — no setup needed.

---

## 📁 Project Structure

```
CybersecurityChatbot/
├── MainWindow.xaml          # WPF GUI layout (Chat, Tasks, Quiz, Activity Log tabs)
├── MainWindow.xaml.cs       # Event handlers for all tabs
├── ChatBot.cs               # Core chatbot logic and NLP intent routing
├── KeywordResponder.cs      # Keyword detection with multiple random responses
├── SentimentDetector.cs     # Detects emotional tone from user input
├── MemoryStore.cs           # Stores user name and favourite topic
├── TaskManager.cs           # Business logic for task add/complete/delete
├── TaskStorageHelper.cs     # JSON read/write using Newtonsoft.Json
├── CyberTask.cs             # Task model class
├── QuizManager.cs           # Quiz logic with 12 questions and scoring
├── QuizQuestion.cs          # Quiz question model class
├── ActivityLogger.cs        # Logs actions with timestamps
├── AudioPlayer.cs           # Plays greeting.wav on launch
├── greeting.wav             # Voice greeting audio file
└── README.md
```

---

## 🔢 GitHub Releases

| Tag | Description |
|-----|-------------|
| `v3.0` | Task assistant and JSON storage working together |
| `v3.1` | Quiz and activity log added and functional |
| `v3.2` | Full integration complete — all three parts working together, final version |

---

## 🖼️ Screenshots

<img width="1920" height="1080" alt="Screenshot 2026-06-26 191226" src="https://github.com/user-attachments/assets/9fc22564-c573-4571-af29-b9757a7d01e2" />

> *(Add a screenshot of the GitHub Actions green tick here)*

---

## 🎥 YouTube Video

> *(Add your unlisted YouTube video link here)*

---

## 📦 Submission Notes

- GitHub repository is set to **Public**
- ZIP backup excludes `bin/` and `obj/` folders
- YouTube video is **Unlisted** and accessible without login
