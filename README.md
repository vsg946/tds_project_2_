# 🤖 Autonomous Data Quiz Solver Agent

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg)](https://www.python.org/downloads/)

This intelligent agent was developed by **Shiva Ganesh V** for the **Tools in Data Science (TDS) course** at IIT Madras. Its core function is to autonomously solve complex, multi-step data analysis quizzes presented as a chain of web pages.

## 💡 Core Technology & Design

The agent is an application of advanced LLM orchestration, designed for robust decision-making and tool use.

* **Orchestrator:** **LangGraph** state machine for managing multi-step flows and decisions.
* **Reasoning Engine:** **Google Gemini 2.5 Flash** directs the execution and planning.
* **Deployment:** Packaged using **FastAPI** and **Docker** for scalable web deployment.


---

## 🛠️ Capabilities

The agent is equipped with specialized tools to handle the entire data analysis lifecycle:

| Capability | Tool Used | Purpose |
| :--- | :--- | :--- |
| **Data Sourcing** | Web Scraper (Playwright) | Renders and extracts content from dynamic (JavaScript-heavy) web pages. |
| **File Handling** | File Downloader | Securely fetches files (CSV, PDF, etc.) referenced in the quizzes. |
| **Analysis** | Code Executor | Writes and runs Python code on demand for data manipulation, statistics, and visualization. |
| **Task Completion** | POST Request | Submits final, calculated answers and handles quiz feedback. |

---

## 🚀 Setup and Usage

### Prerequisites

* Python 3.12+
* uv (recommended package manager) or pip
* Docker (for containerized deployment)

### Installation

1.  Clone the repository and navigate into the directory.
2.  Install dependencies and browser requirements:
    ```bash
    uv sync
    uv run playwright install chromium
    ```

### Configuration

Set the following secrets in a `.env` file for API key and authentication:

```env
EMAIL=your.email@example.com
SECRET=your_secret_string
GOOGLE_API_KEY=your_gemini_api_key_here
