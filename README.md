# ATS Automation Project

This project automates the process of filling Applicant Tracking System (ATS) forms such as **Workday**, using **FastAPI** and **Playwright** with a Chromium browser.

## 🛠 Project Structure

```
ats_automation_project/
│
├── app/
│   ├── main.py                  # FastAPI entrypoint
│   ├── config.py                # Configuration (env, constants)
│   ├── routes/
│   │   └── ats.py               # Route to trigger automation
│   ├── services/
│   │   └── workday_filler.py    # Core logic to fill ATS form (Playwright/Chromium)
│   ├── utils/
│   │   └── logger.py            # Logging utility
│   └── schemas/
│       └── ats_schema.py        # Request/response Pydantic models
│
├── requirements.txt            # Python dependencies
├── playwright.config.ts        # Playwright config (if needed)
├── .env                        # Environment variables
└── README.md                   # You're here!
```

## 🚀 Features

- FastAPI backend with RESTful endpoint to trigger automation.
- Uses Playwright with Chromium to automate ATS job application.
- Modular code structure (routes, services, schemas, utils).
- Logging for debugging and monitoring automation behavior.

## ✅ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/vatsalrishabh/jobautoai-fastapi-playwright.git
cd ats_automation_project
```

### 2. Create and Activate Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate
```

### 3. Install Requirements

```bash
pip install -r requirements.txt
```

### 4. Install Playwright Browsers

```bash
playwright install
```

### 5. Add Environment Variables

Create a `.env` file:

```env
BASE_URL=https://www.example-workday-url.com
CHROME_HEADLESS=true
```

## 📬 API Endpoint

### `POST /ats/apply`

Trigger automation to apply to an ATS job.

#### Request Body Example

```json
{
  "full_name": "John Doe",
  "email": "john@example.com",
  "resume_link": "https://example.com/resume.pdf"
}
```

#### Response

```json
{
  "status": "success",
  "message": "Application submitted successfully"
}
```

## 📚 Docs

- Interactive API docs available at:  
  `http://localhost:8000/docs`

## 🧪 Testing

Use:
- Swagger UI (`/docs`)
- Postman or Insomnia
- curl

Example:

```bash
curl -X POST http://localhost:8000/ats/apply \
-H "Content-Type: application/json" \
-d '{"full_name":"John Doe","email":"john@example.com","resume_link":"https://example.com/resume.pdf"}'
```

## 📄 License

MIT License. Feel free to use, modify, and contribute.

---

Made with ❤️ by [Vatsal Rishabh](https://github.com/vatsalrishabh)