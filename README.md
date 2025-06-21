# 🏛️ OlymPusERP

**OlymPusERP** is a powerful, open-source **ERP system for colleges** that streamlines academic and administrative operations.

Inspired by the grandeur of Mount Olympus, it manages **student records**, **fee automation**, **course scheduling**, and **real-time analytics**—using modern, secure, and scalable technologies.

---

## 🚀 Features

* 📚 **Student Management** – Profiles, enrollment, attendance, grades.
* 💳 **Fee Automation** – Razorpay integration, invoice generation.
* 📆 **Course Scheduling** – Timetables & exam schedules with conflict detection.
* 📊 **Analytics Dashboard** – Powered by Retrieval-Augmented Generation (RAG).
* 🎓 **Student Portal** – Daily interaction with a clean, responsive UI.
* 🔐 **Secure & Scalable** – JWT auth, MySQL, modular APIs.

---

## 🛠️ Tech Stack

### 🧠 Backend

![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge\&logo=django\&logoColor=white)
![DRF](https://img.shields.io/badge/DRF-ff1709?style=for-the-badge\&logo=django\&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge\&logo=mysql\&logoColor=white)

**Libraries**:

* `djangorestframework-simplejwt` ![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge\&logo=jsonwebtokens\&logoColor=white)
* `mysqlclient`
* `python-decouple`
* `django-cors-headers`
* `gunicorn` ![Gunicorn](https://img.shields.io/badge/Gunicorn-499848?style=for-the-badge)

### 💻 Frontend

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge\&logo=react\&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge\&logo=typescript\&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge\&logo=tailwind-css\&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge\&logo=axios\&logoColor=white)

### ☁️ Hosting & Services

![cPanel](https://img.shields.io/badge/cPanel-FF6C2C?style=for-the-badge\&logo=cpanel\&logoColor=white)
![Razorpay](https://img.shields.io/badge/Razorpay-02042B?style=for-the-badge\&logo=razorpay\&logoColor=white)
![Twilio](https://img.shields.io/badge/Twilio-F22F46?style=for-the-badge\&logo=twilio\&logoColor=white)

---

## 🎯 Use Case

OlymPusERP empowers colleges to:

* Automate tasks like reminders and scheduling.
* Replace fragmented systems with one unified solution.
* Use analytics for data-driven decisions.
* Engage students with an intuitive, self-service portal.

---

## 📦 Installation

### 🔧 Prerequisites

* Python 3.10+
* Node.js 18+
* MySQL 8.0+
* Git
* cPanel (for deployment)

---

### ⚙️ Backend Setup

```bash
git clone https://github.com/your-username/OlymPusERP.git
cd OlymPusERP/backend

python -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate

pip install -r requirements.txt
```

Create a `.env` file:

```env
SECRET_KEY=your-secret-key
DEBUG=True
DATABASE_URL=mysql://user:password@localhost/olympus_erp
ALLOWED_HOSTS=localhost,127.0.0.1
RAZORPAY_KEY_ID=your-key
RAZORPAY_KEY_SECRET=your-secret
```

```bash
mysql -u root -p
CREATE DATABASE olympus_erp;

python manage.py migrate
python manage.py runscript seed_data  # Optional
python manage.py runserver
```

---

### 🎨 Frontend Setup

```bash
cd ../frontend
npm install
npm start
```

Access frontend at `http://localhost:3000` and backend API at `http://localhost:8000/api/`.

---

## 🌐 cPanel Deployment

### 📤 Upload Files

Upload `backend/` and `frontend/` to `/home/username/olympus_erp/`

### 🐍 Backend (Python App)

* Python: 3.10+
* Application Root: `/home/username/olympus_erp/backend`
* Application URL: `yourdomain.com`
* WSGI Path: `backend/olympus_erp/wsgi.py`

```bash
cd backend
pip install -r requirements.txt
python manage.py migrate
python manage.py collectstatic
```

Configure `.env` for production MySQL credentials from cPanel.

---

### 🖼️ Frontend (React)

```bash
cd frontend
npm install
npm run build
```

Move `build/` to `public_html/` or your subdomain (e.g., `erp.yourdomain.com`).

Update `axios` base URL to:

```ts
axios.defaults.baseURL = 'https://yourdomain.com/api/';
```

---

## 🧪 Testing

* API: [http://localhost:8000/api/students/](http://localhost:8000/api/students/)
* Frontend: [http://localhost:3000](http://localhost:3000)

---

## 🌟 Contributors

| Contributor                                 | Role               | Portfolio                                   |
| ------------------------------------------- | ------------------ | ------------------------------------------- |
| [Anup Mishra]((https://github.com/Anup2601))      | Frontend Developer | Builds UI using React, TypeScript, Tailwind |
| [Priyesh Pandey](https://priyeshpandey.in/) | Backend Developer  | DRF, MySQL, RAG analytics, integrations     |

---

## 🤝 Contributing

We welcome all contributions!

```bash
git checkout -b feature/your-feature
git commit -m "feat: your feature"
git push origin feature/your-feature
```

Open a Pull Request 🚀

### Code Guidelines

* Python: Follow **PEP 8** using `flake8`
* React: Use **Prettier** & **ESLint**
* Commit Style: Use `feat:`, `fix:`, `chore:`, etc.

---

## 📜 License

This project is licensed under the **MIT License**.
See the [LICENSE](LICENSE) file for full terms.

---

## 📬 Contact

For bugs, issues, or collaboration:

* [Create an Issue](https://github.com/CipherNinja/OlymPusERP/issues)
* Reach out to contributors via their websites

