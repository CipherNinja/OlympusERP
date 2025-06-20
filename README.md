OlymPusERP
Overview
OlymPusERP is a robust, scalable Enterprise Resource Planning (ERP) system designed for colleges to streamline academic and administrative operations. Inspired by the grandeur of Mount Olympus, it serves as the backbone for managing student records, fee payments, course scheduling, and analytics, making daily operations seamless and habit-forming for institutions. Built with modern technologies, it ensures efficiency, security, and ease of use for college administrators, faculty, and students.
Use Case
OlymPusERP empowers colleges to:

Manage Students: Handle student profiles, enrollments, attendance, and grades with an intuitive API-driven interface.
Automate Fees: Process payments and generate invoices, integrating with gateways like Razorpay for seamless transactions.
Schedule Efficiently: Organize courses, timetables, and exams with automated conflict detection.
Gain Insights: Leverage Retrieval-Augmented Generation (RAG) for real-time analytics, delivering daily actionable insights (e.g., enrollment trends, fee collection stats).
Foster Engagement: Provide a student portal and community hub for self-service and interaction, inspired by habit-forming systems like e-commerce platforms.

Ideal for small to medium-sized colleges, OlymPusERP is designed for institutions seeking a cost-effective, all-in-one solution to replace fragmented systems, with a focus on daily operational integration.
Tech Stack
Backend

Django REST Framework (DRF): Powers the API-driven backend for modular, scalable endpoints (e.g., /api/students/).
MySQL: Relational database for storing student, fee, and scheduling data, ensuring performance and reliability.
Python Libraries:
mysqlclient: MySQL database adapter.
python-decouple: Manages environment variables.
djangorestframework-simplejwt: JWT authentication for secure APIs.
django-cors-headers: Enables CORS for frontend integration.
gunicorn: WSGI server for cPanel deployment.


RAG Integration: Planned for analytics, fetching real-time data (e.g., via APIs or web scraping) for insights.

Frontend

React.js with TypeScript: Builds a responsive, type-safe user interface for admin and student dashboards.
Tailwind CSS: Provides modern, customizable styling.
Axios: Handles API requests to the DRF backend.

Hosting

cPanel: Hosts the backend (via WSGI) and frontend (via static file serving), with MySQL managed through cPanel’s database tools.

Installation Process
Prerequisites

Python 3.10+: For backend development.
Node.js 18+: For frontend development.
MySQL 8.0+: For the database.
cPanel Hosting: With Python App Setup and MySQL support.
Git: For cloning the repository.

Local Development Setup

Clone the Repository
git clone https://github.com/your-username/OlymPusERP.git
cd OlymPusERP


Backend Setup

Navigate to the backend folder:cd backend


Create a virtual environment:python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


Install dependencies:pip install -r requirements.txt


Create a .env file in backend/ with the following:SECRET_KEY=your-secret-key
DEBUG=True
DATABASE_URL=mysql://user:password@localhost/olympus_erp
ALLOWED_HOSTS=localhost,127.0.0.1
RAZORPAY_KEY_ID=your-key
RAZORPAY_KEY_SECRET=your-secret


Set up MySQL database:mysql -u root -p
CREATE DATABASE olympus_erp;


Run migrations:python manage.py migrate


Seed initial data (optional):python manage.py runscript seed_data


Start the development server:python manage.py runserver




Frontend Setup

Navigate to the frontend folder:cd frontend


Install dependencies:npm install


Start the development server:npm start


The React app will run at http://localhost:3000, connecting to the backend API at http://localhost:8000.


Testing Locally

Access the backend API at http://localhost:8000/api/ (e.g., /api/students/).
Test frontend features via the React app, ensuring CORS is configured in backend/olympus_erp/settings.py.



cPanel Deployment

Upload Files

Use cPanel’s File Manager to upload the backend and frontend folders to /home/username/olympus_erp/.
Alternatively, use FTP or Git to deploy.


Backend Configuration

In cPanel, go to Setup Python App:
Select Python 3.10+.
Set Application Root to /home/username/olympus_erp/backend.
Set Application URL to your domain (e.g., yourdomain.com).
Point WSGI to backend/olympus_erp/wsgi.py.


Install dependencies via cPanel’s Terminal:cd /home/username/olympus_erp/backend
pip install -r requirements.txt


Create MySQL database in cPanel’s MySQL Databases:
Name: olympus_erp.
Create a user and grant all privileges.
Update backend/.env with database credentials.


Run migrations:python manage.py migrate


Collect static files:python manage.py collectstatic




Frontend Configuration

Build the React app:cd /home/username/olympus_erp/frontend
npm install
npm run build


Move the build/ folder to cPanel’s public_html or a subdomain (e.g., erp.yourdomain.com).
Update API URLs in the frontend (e.g., axios.defaults.baseURL = 'https://yourdomain.com/api/').


Final Steps

Restart the Python app in cPanel.
Configure cron jobs for backups (backend/scripts/backup_db.py).
Test the deployed app at yourdomain.com (frontend) and yourdomain.com/api/ (backend).



Contributors

Priyesh Pandey - Backend Developer  
Responsible for Django REST Framework APIs, MySQL database design, and RAG integration for analytics.


Anup Mishra - Frontend Developer  
Handles TypeScript + React.js development, Tailwind CSS styling, and frontend-backend integration.



Contributing
We welcome contributions! To contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/your-feature).
Commit changes (git commit -m 'Add feature').
Push to the branch (git push origin feature/your-feature).
Open a Pull Request.

Please follow the code style in backend/ (e.g., PEP 8 for Python) and frontend/ (e.g., Prettier for TypeScript).
License
MIT License. See LICENSE for details.

📞 Contact -- For issues or suggestions, create a GitHub issue or reach out to the contributors.
🌐 Anup Mishra - https://Anupmishra.com/
🌐 Priyesh Pandey - https://priyeshpandey.in/

