# 🤖 AI-Powered Resume Tailoring Automation with n8n + Gemini + ScrapingDog

This project is a no-code, end-to-end system built using **n8n**, which tailors user resumes for each job description scraped from LinkedIn using ScrapingDog, enhances them with Gemini AI, and stores the output in Google Sheets.

---

## ✨ Features

- ✅ Scrapes live job listings from LinkedIn using ScrapingDog API
- ✅ Extracts job descriptions and recruiter info
- ✅ Accepts user resumes via a form (n8n webhook UI)
- ✅ Uses Google Gemini AI (via Vertex or API) to generate tailored resumes
- ✅ Loops through every job row from Google Sheets and matches resume
- ✅ Stores tailored resumes into Google Sheets
- ✅ 100% automated, no manual effort required

---

## 🧠 Tech Stack

| Tool            | Purpose                                  |
|------------------|------------------------------------------|
| n8n              | Workflow automation engine               |
| ScrapingDog API  | LinkedIn job data scraping               |
| Google Sheets    | Store scraped job + tailored resume data |
| Gemini AI        | AI resume generator                      |
| Google Drive     | (Optional) Upload `.docx` files          |

---

## 🔁 Workflow Structure

### Phase 1: Scrape Jobs & Store

```

Webhook (form trigger)
↓
Get Job Details (ScrapingDog LinkedIn Jobs API)
↓
Split Job IDs
↓
Get Job Overview
↓
Save in Google Sheet (Job Data)

```

### Phase 2: Resume Tailoring with AI

```

On Resume Submission (n8n form trigger)
↓
Read Job Descriptions (from Sheet)
↓
Loop over each job (SplitInBatches)
↓
Send resume + JD to Gemini AI
↓
Store tailored resume in Google Sheets

````

---

## 🚀 How to Use

### 1. Clone the repo

```bash
git clone https://github.com/yourusername/ai-resume-tailor-n8n.git
cd ai-resume-tailor-n8n
````

### 2. Import Workflow into n8n

* Open [n8n.io](https://n8n.io)
* Click `Import Workflow` and select `Resume Tailor.json` from this repo.

### 3. Configure Environment

* 🔐 ScrapingDog API Key
* 🔐 Google Sheets (OAuth or Service Account)
* 🔐 Gemini AI access (via Vertex AI or OpenRouter)

### 4. Setup Google Sheet

Use the following column headers in your sheet:

\| Job Title | Location | Description | Job Link | Recruiter Name | Recruiter Title | Recruiter Profile URL | Tailored Resume | Status |

---

## 🧠 Prompt Used for Resume Tailoring

```
You are a professional resume builder. Use the user's resume and match it to the job description below. Highlight keywords, skills, and align the summary, skills, experience, and projects sections to match the job post. Ensure it's ATS-friendly and professionally formatted in plain text or markdown.
```

---

## 🖼️ Demo Graphic

![Workflow Demo](./assets/ai-resume-tailor.png)

---

## 📦 Files

| File                   | Description                     |
| ---------------------- | ------------------------------- |
| `Resume Tailor.json`   | Exported n8n workflow           |
| `Screenshot.png`       | Visual of the flow              |
| `README.md`            | This file                       |
| `ai-resume-tailor.png` | LinkedIn/social preview graphic |

---

## 🧩 Optional Add-ons

* Convert generated markdown/text to `.docx` using Pandoc or CloudConvert
* Upload files to Google Drive & generate shareable links
* Trigger Telegram alert when each resume is completed

---

## 📣 Contribute / Fork

Want to build a freelance or career product out of this?
Feel free to fork it, remix, or use this as your personal AI assistant.

---

## 🙌 Built By

Follow my AI automation builds [LinkedIn](https://linkedin.com/in/your-profile)

---

## 🏷️ Tags

`n8n` `AI automation` `resume builder` `gemini AI` `scrapingdog` `openrouter` `job search` `linkedin tools` `cold email` `workflow automation`

```

