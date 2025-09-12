# 🚀 Automated Job Search & Cover Letter Generator with Match Scoring (n8n + Gemini)

## 📌 Project Description
This project automates the process of job searching, resume-job matching, and cover letter generation.  
Using **n8n** for orchestration and **Google Gemini** for AI-powered cover letter creation, the system fetches job listings, evaluates their match score with your resume, generates personalized cover letters, stores details in Google Sheets, and sends you a **daily email summary** of the best job matches.

---

## ✨ Features
- 🔍 **Automated Job Fetching** from Google Jobs (SerpAPI) 
- 📊 **Resume-Job Match Scoring** via Gemini(`/score`)  
- ✍️ **Personalized Cover Letter Generation** via Gemini (`/cover-letter`)  
- 📑 **Data Storage in Google Sheets** for tracking jobs and applications  
- 📧 **Daily Email Summary** with top N job matches  

---

## ⚙️ Tech Stack
- **n8n** → Workflow Orchestration  
- **FastAPI** → Microservice for scoring & cover letter API  
- **Google Gemini API** → Cover letter generation  
- **SerpAPI** → Job search  
- **Google Sheets** → Data storage  
- **SMTP / Gmail** → Daily email notifications  

---

## 📂 Repository Structure

job-automation-project/
│
├── n8n_workflow/
│ └── n8n_job_auto.json # Exported n8n workflow
│
├── prompts/
│ ├── cover_letter.txt # Cover letter prompt template
│ └── profile_extract.txt # Resume skill extraction prompt
│
├── screenshots/
│ ├── google_sheets.png
│ ├── email_summary.png
│ └── n8n_workflow.png
│
└── README.md

## 🛠️ Setup & Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/job-automation-project.git
cd job-automation-project
```

### 2️⃣ Setup n8n Workflow

Import n8n_workflow/n8n_job_auto.json into your n8n instance.

Configure credentials:

SerpAPI (Google Jobs)

Google Sheets API

Gmail / SMTP

FastAPI endpoint (http://127.0.0.1:8000)

Activate workflow.

📬 Workflow Diagram

📊 Sample Outputs

Google Sheets:
![Google Sheet](https://github.com/user-attachments/assets/43b66101-c920-4463-a126-844d1f44852f)

n8n Workflow:
![n8n workflow](https://github.com/user-attachments/assets/ca14d250-5cd8-4b0c-9989-fdc1028e616f)

Email Summary:
![email1](https://github.com/user-attachments/assets/2a520567-edf9-4382-ad18-0880279f83a6)

![email2](https://github.com/user-attachments/assets/e5d8408b-bb1d-4dd3-b3d6-49fca3a4c5fa)




📝 How It Works

Scheduled Trigger (9:30 AM IST) → Runs daily.

Job Fetch → Queries SerpAPI for job listings.

Normalize Data → Standardizes job details (title, company, URL, etc.).

Match Scoring → Calls FastAPI /score endpoint.

Cover Letter → Calls FastAPI /cover-letter (Gemini).

Google Sheets → Appends job + score + cover letter.

Sort & Select Top N Jobs → Highest scores kept.

Email Summary → Sends formatted summary with job links.

📌 Future Improvements

🔧 Support LinkedIn & Naukri job scraping

📈 Advanced ML-based scoring instead of keyword matching

🌐 Deploy FastAPI service to cloud (Render / Vercel / AWS)

📱 Telegram/Slack bot for instant job notifications

👨‍💻 Author

Syed Shakir Sayeed 

🔗 LinkedIn link:[syed-shakir-sayeed-776a6229a]
