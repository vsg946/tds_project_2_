# **LLM Analysis Quiz Solver**
**Developer: Shiva Ganesh**

This project is an autonomous FastAPI-based agent that solves multi-step quiz tasks using LangGraph, LangChain, Playwright, and Google Gemini. It can scrape webpages, run Python code, download files, analyze data, and automatically submit answers. The agent takes a quiz URL, processes each page, and continues until all tasks are completed.

## **Run Locally**
```bash
pip install uv
uv sync
uv run main.py
