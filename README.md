# DA22_personal_fin_app

# 🐷 Personal Finance Assistant

A smart personal spending tracker powered by OpenAI and Google Apps Script — designed to turn your natural language notes into structured financial records in Google Sheets.

---

## ✨ Features

- 💬 Accepts natural language spending notes (e.g. `Mua sữa 25k`, `Lương tháng 6: 12tr`)
- 🧠 Uses OpenAI GPT (via API) to extract:
  - Who spent/earned
  - Description
  - Date
  - Amount (converted to VND)
  - Flow (income/expense)
  - Purpose category
- 📊 Logs each entry to Google Sheets automatically
- 🌐 Clean, minimal HTML UI — deployable as a GitHub Pages site

---

## 🚀 How It Works

### 1. HTML Form (Frontend)

- Takes multi-line input (one entry per line)
- Sends to Google Apps Script via `fetch()`
- Displays result feedback (`✅ 3 processed, ❌ 1 failed`)

### 2. Google Apps Script (Backend)

- Handles POST requests
- For each line:
  - Calls OpenAI API with a structured classification prompt
  - Validates JSON result
  - Appends it to a connected Google Sheet

---

## 🛠 Setup

### 🔐 Requirements

- OpenAI API key
- A Google Sheet to store data
- A deployed [Google Apps Script Web App](https://developers.google.com/apps-script/guides/web)

### 📦 Instructions

1. **Set up your Google Apps Script:**
   - Copy code from [`Code.gs`](./Code.gs)
   - Set `OPENAI_API_KEY` in Script Properties
   - Set your `SHEET_ID` and `SHEET_NAME`
   - Deploy as Web App (set access to *Anyone*)

2. **Customize your HTML:**
   - Edit `index.html`
   - Replace the script URL with your Web App endpoint

3. **(Optional) Host with GitHub Pages:**
   - Make your repo public if needed
   - Enable GitHub Pages on `main` or `/docs`

---

## 🧪 Example Input

Mua sữa 25k
Cafe 50k
Lương tháng 6: 12tr


### ➡️ Output (in Google Sheets):

| Timestamp | Original | Who | Description | Date | Amount (VND) | Flow | Purpose |
|-----------|----------|-----|-------------|------|---------------|------|---------|
| 14/06/2025 | Mua sữa 25k | pony | Mua sữa cho bé | 14/06/2025 | 25000 | expense | Necessities |

---

## 📄 File Structure
├── index.html # Frontend UI
├── README.md
├── Code.gs # Google Apps Script backend

---

## 🧩 Tech Stack

- OpenAI GPT-4o API
- Google Apps Script (Web App)
- HTML + JS
- Google Sheets

---

## 🙌 Credits

Developed by Neo Nguyen  
Icons: 🐷 🦄 🍉 (Pig, Unicorn, Watermelon) represent my family 🎉

---

## 📜 License

MIT — free to use, modify, and improve.
