  # ☕ AI Cafe Feedback Agent (n8n)

🚀 An AI-powered customer feedback automation system that **analyzes, categorizes, and routes feedback in real-time** using n8n, OpenAI, Google Sheets, and Gmail.

This workflow helps businesses automatically process customer reviews and send them to the right team—without manual effort.

---

## 🎯 Project Highlights

* 📥 Detects new feedback entries in Google Sheets
* 🤖 Uses AI to classify feedback into:

  * Category (question, problem, suggestion, etc.)
  * Business Area (kitchen, delivery, service)
* 🔄 Updates the sheet with AI-generated labels
* 📧 Automatically routes feedback to the correct team via email
* ⚡ Works in real-time (trigger-based automation)

---

## 🧠 How It Works

1. Google Sheets Trigger detects a new feedback row
2. Data is extracted (Name, Contact, Feedback, Timestamp)
3. AI Agent analyzes the feedback
4. Feedback is classified into:

   * Category (problem, question, suggestion, etc.)
   * Area (kitchen, delivery, service, other)
5. Results are written back to Google Sheets
6. Workflow routes feedback:

   * Kitchen → Kitchen team
   * Delivery → Delivery team
   * Service → Service team
   * Unknown → fallback email

---

## 🏗️ Workflow Architecture

```text
Google Sheets Trigger
        ↓
Extract Data
        ↓
AI Categorization (OpenAI)
        ↓
Normalize Labels
        ↓
Update Google Sheet
        ↓
IF (unknown?)
        ↓
Route by Area
        ↓
Gmail (Send to respective team)
```

---

## 📸 Screenshots

### 🔹 Workflow Overview

<img width="2048" height="578" alt="cafe-feedback_workflow" src="https://github.com/user-attachments/assets/03c494cf-354d-4727-90a7-2acd332d2782" />

### 🔹 Example Email Notification

<img width="2047" height="755" alt="feedback_email" src="https://github.com/user-attachments/assets/eba7d7b3-2a72-4f69-8cc7-d282043814c2" />

---

## 🧩 Workflow Components

| Component             | Purpose                     |
| --------------------- | --------------------------- |
| Google Sheets Trigger | Detects new feedback        |
| Extract Data          | Cleans input data           |
| AI Agent              | Classifies feedback         |
| Output Parser         | Ensures structured response |
| Normalize Labels      | Standardizes results        |
| Google Sheets Update  | Stores classification       |
| IF Node               | Handles unknown cases       |
| Switch Node           | Routes feedback             |
| Gmail Nodes           | Sends alerts to teams       |

---

## 🛠️ Tech Stack

* **Automation:** n8n
* **AI Model:** OpenAI GPT
* **Database:** Google Sheets
* **Notifications:** Gmail

---

## 📊 Google Sheets Setup

Create a sheet with columns:

```text
ID | Timestamp | Name | Contact | Feedback | Category | Area
```

---

## ⚙️ Setup Guide

### 1. Import Workflow

* Open n8n
* Go to **Workflows → Import from File**
* Upload `ai-cafe-feedback-agent.json`

### 2. Connect Credentials

* Google Sheets OAuth
* Gmail OAuth
* OpenAI API

### 3. Configure Sheet

* Add your spreadsheet ID
* Map the correct sheet

### 4. Configure Email Nodes

Update recipient emails for:

* Kitchen team
* Delivery team
* Service team
* Fallback

### 5. Activate Workflow

* Turn on workflow
* It will run automatically when new feedback is added

---

## 💬 Example Output

```text
Feedback: "My coffee was cold and service was slow"

Category: problem
Area: service
```
---

## 📁 Project Structure

```text
ai-cafe-feedback-agent/
├── ai-cafe-feedback-agent.json
├── README.md
├── assets/
│   ├── workflow.png
│   └── email.png
├── .gitignore
└── LICENSE
```

---

## 🧑‍💻 What This Project Shows

* AI-powered text classification
* Workflow automation design
* Real-time event-driven systems
* Data processing and normalization
* Multi-branch routing logic
* Business process automation

---

## ⭐ Future Improvements

* Add sentiment analysis
* Add dashboard (Power BI / Tableau)
* Store data in database (PostgreSQL / Firebase)
* Add Slack / WhatsApp notifications
* Add priority scoring

---
