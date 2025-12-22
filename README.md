CS50 Final Project – CV Analyzer
by Ayham Abdulkareem Taha
________________________________________
Project Description
CV Analyzer is a backend-focused web application built using Python and Django that helps users analyze their CVs and improve them in a structured and data-driven way. The main idea behind this project is to bridge the gap between a user’s current skills and the skills required by modern job markets.
The application allows users to upload their CV files in PDF or DOCX format. Once uploaded, the system extracts the textual content of the CV, analyzes it, and identifies the technical skills that are already present. After that, it detects the missing skills by comparing the extracted skills against predefined or inferred skill sets related to common career paths.
In addition to identifying skills, the project generates a personalized learning roadmap. This roadmap includes suggested skills to learn, estimated learning time for each skill, and recommended online resources. The goal is not only to analyze the CV but also to guide the user step-by-step toward improving it in a practical way.
This project was developed as the final project for Harvard’s CS50x course, and it reflects the integration of concepts learned throughout the course, including problem-solving, backend development, APIs, and real-world application design.
________________________________________
Motivation and Idea
Many people struggle to understand why their CV is not competitive or what exact skills they are missing. Most tools only provide generic feedback. The motivation behind CV Analyzer was to build a tool that provides actionable feedback, not just analysis.
Instead of telling the user “your CV is weak,” the system explains:
•	What skills are already strong
•	What skills are missing
•	What to learn next
•	Where to learn it
•	How long it might take
This makes the project practical, educational, and directly useful.
________________________________________
Tech Stack
The project was implemented using the following technologies:
•	Python 3.11 – Core programming language
•	Django 4.x – Backend framework
•	Django REST Framework – For building RESTful APIs
•	python-docx – To extract text from DOCX files
•	PyMuPDF / PyPDF2 – To extract text from PDF files
•	MongoDB – Used as the database
•	Postman – Used for testing API endpoints
The backend-only approach was chosen to focus on logic, data processing, and API design rather than frontend complexity.
________________________________________
Features
•	Upload CV files in PDF or DOCX format
•	Automatic extraction of text from CV files
•	Detection of existing technical skills
•	Identification of missing or weak skills
•	Generation of a personalized learning roadmap
•	Estimated learning time for each missing skill
•	Recommended online learning resources
•	REST API endpoint for easy integration
•	Fully tested using Postman
________________________________________
Project Structure
cv-analyzer/
│── analyzer/            # Main Django application
│── cv_analyzer/         # Django project configuration
│── manage.py
│── requirements.txt
│── README.md
Each file and folder was organized to keep the project clean, readable, and maintainable.
________________________________________
Installation & Setup (Run Locally)
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
5. Start the Django server
python manage.py runserver
6. Open in browser
http://127.0.0.1:8000/
________________________________________
API Usage (Postman Example)
Endpoint
POST /analyze/
Request Body (form-data)
Key	Type	Description
cv_file	File	CV (PDF or DOCX)
Example Workflow
1.	Open Postman
2.	Create a POST request
3.	URL:
http://127.0.0.1:8000/analyze/
4.	Go to Body → form-data
5.	Add:
o	Key: cv_file
o	Type: File
6.	Upload a CV file and click Send
Example Response
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
________________________________________
Design Decisions
Several design choices were carefully considered:
•	A REST API approach was used to allow future frontend or mobile integration.
•	Skill analysis was implemented in a modular way to allow easy expansion.
•	MongoDB was chosen for flexibility in handling unstructured data.
•	The project focuses on clarity and usefulness rather than UI complexity.
________________________________________
Demo Video
YouTube Demo:
👉 https://youtu.be/Nysv3SS0TlQ
________________________________________
Requirements
All required Python libraries are listed in requirements.txt.
To generate it:
pip freeze > requirements.txt
________________________________________
Author
Ayham Abdulkareem Taha
Email: ayhamtaha10@gmail.com
________________________________________
Challenges and Limitations
During the development of this project, several challenges were encountered. One of the main difficulties was handling different CV formats, as PDF and DOCX files can vary significantly in structure and encoding. Extracting clean and readable text required experimenting with multiple libraries such as PyMuPDF and PyPDF2 to ensure accuracy and reliability.
Another challenge was designing a skill extraction mechanism that balances simplicity and usefulness. Since CVs are written in many styles, detecting skills reliably without using heavy machine learning models required careful keyword matching and structuring of the analysis logic.
Time estimation for learning skills was also a design challenge. The solution implemented provides approximate learning durations based on common online learning paths, acknowledging that actual learning time may vary from person to person.
Despite these challenges, the project successfully achieves its main objectives while remaining extensible for future improvements.
________________________________________
Future Improvements
While CV Analyzer is functional and effective in its current state, there are several areas where it can be improved in the future:
•	Adding a frontend interface using React or Next.js to improve user experience
•	Integrating real job descriptions to compare CVs against specific roles
•	Using machine learning or NLP models to improve skill extraction accuracy
•	Supporting additional file formats
•	Adding user authentication and profile history
•	Deploying the project to a cloud platform
These improvements would allow the project to scale and become a fully production-ready application.
________________________________________
What I Learned from This Project
Working on this project helped me apply many concepts learned throughout CS50x in a practical way. I gained deeper experience with backend development, API design, and structured problem-solving.
I also improved my understanding of:
•	Django project organization
•	REST API development
•	Handling file uploads securely
•	Working with external libraries
•	Writing clear and professional technical documentation
Most importantly, this project strengthened my confidence in building complete software solutions from idea to implementation.
________________________________________
Testing and Validation
All API endpoints were manually tested using Postman to ensure correctness and reliability. Multiple CV samples were used to validate skill extraction, missing-skill detection, and roadmap generation. Error handling was implemented to manage invalid files or empty uploads gracefully.
Testing focused on ensuring consistent API responses and meaningful output rather than UI-level validation.
________________________________________
Conclusion
CV Analyzer is a practical and extensible backend project that demonstrates the ability to design, build, and document a real-world software solution. It aligns well with the objectives of CS50x by combining technical depth, creativity, and usability into a single coherent project.

Final Notes
This project represents my learning journey throughout CS50x and demonstrates my ability to design, implement, and document a complete software project. It combines technical skills with real-world usefulness and serves as a strong foundation for future development.
