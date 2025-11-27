# **LLM Analysis Quiz Solver**
### **Autonomous Multi-Step Quiz Solving Agent**
**Developer: Shiva Ganesh**

---

# **Overview**
The LLM Analysis Quiz Solver is an autonomous agent that uses LangGraph, LangChain, FastAPI, Playwright, and Google Gemini to solve multi-step quiz tasks. It can scrape webpages, extract data, run Python code, download files, analyze information, and automatically submit answers. Once a quiz URL is provided, the agent processes each page until the entire quiz sequence is completed.

---

# **Key Features**
- Fully autonomous quiz solving  
- JavaScript rendering using Playwright  
- Python code execution for analysis  
- File downloading and parsing  
- On-the-fly dependency installation  
- FastAPI backend for REST integration  
- Docker-ready deployment (HuggingFace / Railway)  
- LangGraph-based decision engine  

---

# **Architecture**
FastAPI → LangGraph Agent → Tools Layer  
  ├─ Web Scraper  
  ├─ Downloader  
  ├─ Code Executor  
  ├─ POST Request Sender  
  └─ Dependency Installer  

The agent uses a state-machine approach where each step of the quiz is executed based on reasoning from the LLM.

---

# **Project Structure**
  main.py                 → FastAPI server and /solve endpoint  
  agent.py                → LangGraph agent logic  
  tools/                  → Modular tool functions  
      web_scraper.py  
      download_file.py  
      code_generate_and_run.py  
      send_request.py  
      add_dependencies.py  
  pyproject.toml          → Dependencies  
  Dockerfile              → Container image  
  README.md               → Documentation  

---


---



---



# **Docker Deployment**

Build the image:  
docker build -t llm-agent .

Run the container:  
docker run -p 7860:7860  
  -e EMAIL="24f2001081@ds.study.iitm.ac.in"  
  -e SECRET="JD_IN"  
  -e GOOGLE_API_KEY="your_api_key"  
  llm-agent  

---

# **How It Works**
1. FastAPI receives the quiz URL  
2. LangGraph initializes an agent with memory  
3. The agent analyzes the page and selects the required tools  
4. Tools scrape, download, compute, or analyze data  
5. The result is generated and submitted  
6. If more quiz pages exist, the agent continues automatically  
7. The chain ends when no new URL is found  

---

# **Author**
**Shiva Ganesh**  
Tools in Data Science – IIT Madras  
For issues, please open a GitHub issue.

