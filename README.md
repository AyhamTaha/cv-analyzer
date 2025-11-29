CS50 Final Project – CV Analyzer by Ayham Abdulkareem Taha

📌 Project Description
CV Analyzer is a Python/Django-based tool that reads CVs (PDF/DOCX), extracts skills, and analyzes them to generate:
✅ Skills Found
❌ Skills Missing
🧭 Personalized Roadmap with estimated learning time
🔗 Recommended Resources for each missing skill
This project helps users improve their CVs and learn new skills efficiently.

🛠 Tech Stack
Python 3.11
Django 4.x
Django REST Framework
python-docx
PyMuPDF / PyPDF2
MongoDB

🚀 Features
Upload CV (PDF / DOCX)
Automatic skill detection
Missing-skill analysis
AI-like learning roadmap generation
REST API endpoint

Tested with Postman
---

## Setup Instructions
1. Clone this repository:
   ```bash
   git clone https://github.com/AyhamTaha/cv-analyzer.git

   🔧 Installation & Setup (Run Locally)
1. Clone the repository
git clone https://github.com/AyhamTaha/cv-analyzer.git
cd cv-analyzer

2. Create and activate virtual environment
Windows:
python -m venv venv
venv\Scripts\activate


3. Install dependencies
pip install -r requirements.txt

4. Run migrations
python manage.py migrate

5. Start Django server
python manage.py runserver

6. Open in browser
http://127.0.0.1:8000/

📡 API Usage (Postman Example)
Endpoint
POST /analyze/

Body (form-data)
Key	Type	Description
cv_file	File	CV in PDF or DOCX
Example using Postman

Open Postman

Create POST request

URL:
http://127.0.0.1:8000/analyze/


Go to Body → form-data

Add:
Key: cv_file
Type: File
Upload CV (pdf/docx)

Send request
Response Example:

{
  "skills_found": ["Python", "Django", "SQL"],
  "skills_missing": ["Docker", "REST APIs"],
  "roadmap": [
    {
      "skill": "Docker",
      "hours": 10,
      "resource": "https://docker-curriculum.com/"
    }
  ]
}

📺 Demo Video

YouTube Demo:
👉 https://youtu.be/Nysv3SS0TlQ


📦 Requirements
This project uses the libraries listed in requirements.txt.
To generate it:
pip freeze > requirements.txt

👨‍💻 Author
Ayham Abdulkareem Taha
Email: ayhamtaha10@gmail.com


