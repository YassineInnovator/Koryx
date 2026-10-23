# Koryx

> Hardware telemetry meets local intelligence.

Koryx is an intelligent Windows desktop utility combining real-time hardware telemetry with AI-powered diagnostics. Built on Tauri, React, and Python, it monitors CPU, RAM, and disk metrics, persisting time-series data locally in SQLite. Ask the integrated AI to explain your system's behavior naturally. Hardware monitoring meets local intelligence.

---

## ⚡ Features

- **Real-Time Telemetry:** Live monitoring of CPU utilization, frequency, RAM consumption, storage capacity, and network throughput.
- **Time-Series Persistence:** High-frequency metrics are stored efficiently in a local SQLite database utilizing Write-Ahead Logging (WAL) for seamless historical performance charts.
- **Intelligent Alerts:** Configurable threshold warnings (e.g., sustained CPU spikes) with built-in hysteresis to prevent notification spam.
- **Context-Aware AI Diagnostics:** Feed live, sanitized hardware context to either a local AI model (Ollama) or cloud AI (Gemini) to ask natural-language questions about your PC's behavior.
- **Native Windows Experience:** Packaged as a sleek, native desktop application using Tauri, featuring a premium dark-themed UI built with Tailwind CSS.

## 🏗️ Architecture

Koryx separates the heavy lifting from the user interface:
1. **The Glass (Frontend):** A React/TypeScript Single Page Application (SPA) providing a fast, responsive dashboard.
2. **The Shell (Tauri):** A lightweight Rust binary that manages the OS window, system tray, and native notifications.
3. **The Engine (Backend):** An independent Python (FastAPI) background process that gathers `psutil` metrics, manages the SQLite database, and handles AI API integrations.

## 🛠️ Tech Stack

- **Frontend:** React 18, TypeScript, Vite, Tailwind CSS, Lucide Icons
- **Desktop Shell:** Tauri v2 (Rust)
- **Backend:** Python 3, FastAPI, Uvicorn, psutil
- **Database:** SQLite3 (WAL Mode)

---

## 🚀 Getting Started

### Prerequisites
To build and run Koryx locally, you will need the following installed on your Windows machine:
- [Node.js](https://nodejs.org/) (v18+)
- [Python](https://www.python.org/downloads/) (v3.10+)
- [Rust & Cargo](https://rustup.rs/)
- Visual Studio C++ Build Tools (Required for compiling Rust and Python packages like `psutil`)

### 1. Clone the Repository
```powershell
git clone [https://github.com/yourusername/koryx.git](https://github.com/yourusername/koryx.git)
cd koryx
