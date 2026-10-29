# EduXplain — Student Performance & Academic Risk Prediction

EduXplain is a Flask web application that helps identify students who may be academically at risk using performance and engagement indicators. It accepts student data, requests an AI-generated assessment through the Gemini API, and presents a risk prediction, reasons, and recommendations.

## Features
- User registration, login, and logout
- Student risk assessment using attendance, quiz scores, assignment scores, class participation, prior-topic scores, and weekly study hours
- AI-generated prediction explanations and recommendations
- Optional Tamil and Hindi recommendations when returned by the model
- Prediction records stored using SQLAlchemy
- SQLite for local development and PostgreSQL when `DATABASE_URL` is configured
- Responsive web interface

## Tech stack
Python, Flask, HTML, CSS, JavaScript, Flask-SQLAlchemy, SQLite/PostgreSQL, Google Gemini API.

## Run locally
1. Install Python 3.12 or a compatible version.
2. Create and activate a virtual environment.
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set your Gemini API key:
   - Windows PowerShell: `$env:GEMINI_API_KEY="your_api_key"`
   - macOS/Linux: `export GEMINI_API_KEY="your_api_key"`
5. Start the application:
   ```bash
   python app.py
   ```
6. Open http://127.0.0.1:5000 and register an account.

The local SQLite database is created automatically under `data/eduxplain.db`. Never commit API keys, environment files, or personal database files.

## Configuration
- `GEMINI_API_KEY`: required for AI predictions.
- `DATABASE_URL`: optional PostgreSQL connection URL; otherwise SQLite is used.
- `SECRET_KEY`: set a strong value for deployment.

## Project structure
```
.
├── app.py
├── requirements.txt
├── src/
│   ├── alerts.py
│   ├── auth.py
│   ├── database.py
│   ├── gemini_api.py
│   ├── storage.py
│   └── utils.py
├── templates/
│   ├── index.html
│   ├── login.html
│   └── register.html
└── static/
    ├── favicon.svg
    └── style.css
```

## Responsible use
AI-generated risk scores are only supportive indicators, not definitive judgments. Educators should consider the student's wider context before making decisions.
