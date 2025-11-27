# 🚀 Automated Quiz Solver (FastAPI + Playwright)

This project implements an automated quiz solver for the **TDS LLM Analysis Assignment**.  
The server receives quiz tasks, validates secrets, loads JavaScript-rendered quiz pages using
Playwright, extracts instructions/data, processes files (PDF/CSV/etc.), computes the correct answer,
and submits it back — all within the mandatory **3-minute limit**.


---

## ✅ Features

- ✔ Secret validation (403 for wrong secret)  
- ✔ Handles JavaScript-rendered quiz pages (Playwright)  
- ✔ Extracts embedded Base64 (`atob()`) quiz data  
- ✔ Downloads PDF / CSV / JSON automatically  
- ✔ Processes PDF tables (pdfplumber)  
- ✔ Processes CSV/Excel/JSON (pandas)  
- ✔ Automatically finds & follows next quiz URLs  
- ✔ Submits answers in required JSON format  
- ✔ Finishes entire quiz chain within 3 minutes  

---

## ⚙️ Setup Instructions (Local)

### 1️⃣ Install Python 3.10+

### 2️⃣ Create virtual environment
```
python -m venv venv
```

### 3️⃣ Activate virtual environment

#### Windows CMD:
```
venv\Scripts\activate.bat
```

#### PowerShell:
```
venv\Scripts\Activate.ps1
```

#### Mac/Linux:
```
source venv/bin/activate
```

### 4️⃣ Install dependencies
```
pip install -r requirements.txt
python -m playwright install chromium
```

### 5️⃣ Create `.env`

```
YOUR_SECRET=your-secret-here
YOUR_EMAIL=your-email@example.com
google_api=your-api-token
```

Save it as `.env`.

### 6️⃣ Start the server
```
uvicorn app:app --host 0.0.0.0 --port 8000
```


---



Output includes:
- Computed answer  
- Submission result  
- Next quiz URL (if any)  
- Total runtime  

---

## 🌐 Deployment (Render / Railway / Heroku)

1. Upload this repository to GitHub  
2. Create a new web service on:  
   huggingface
3. Set environment variables:  
   - `YOUR_SECRET`  
   - `YOUR_EMAIL`
   - `YOUR_GOOGLE API KEY`
4. Build commands:
```
pip install -r requirements.txt
python -m playwright install chromium
```
5. Start command:
```
uvicorn app:app --host 0.0.0.0 --port $PORT
```

Your deployment will automatically have HTTPS (required for evaluation).

---


### API Endpoint URL  
Your deployed URL + `/solve`

### GitHub Repo URL  
Link to this repository.

---



## 📜 License
Released under the **MIT License**.

---

## 👨‍💻 Author
Shiva Ganesh V
