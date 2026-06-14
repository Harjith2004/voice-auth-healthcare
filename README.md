🎙️ Voice-Based Authentication System for Healthcare

> A secure voice biometric authentication platform for healthcare applications — built with React.js frontend, Java Spring Boot backend, Python FastAPI ML service, and MySQL database. Replaces traditional passwords with voice recognition to protect patient data privacy.

![Voice Auth Preview](screenshots/login.png)

## 🔗 Links

- 🌐 **Live Demo:** [harjith2004.github.io/voice-auth-healthcare](https://harjith2004.github.io/voice-auth-healthcare)
- 💻 **GitHub:** [github.com/Harjith2004/voice-auth-healthcare](https://github.com/Harjith2004/voice-auth-healthcare)

---

## ✨ Features

- 🎤 **Voice Biometric Login** — Authenticate using your unique voice pattern
- 🔐 **Role-Based Access Control** — Doctor, Nurse, Admin roles with different permissions
- 🏥 **Patient Record Management** — Secure access to electronic health records
- 📋 **Audit Logging** — Every login attempt and record access is tracked
- 🔒 **Account Lockout** — Auto-lock after 3 failed voice attempts
- 📊 **Confidence Scoring** — Real-time voice match confidence display
- 🛡️ **JWT Authentication** — Secure session management
- 🧠 **GMM Voice Model** — Gaussian Mixture Model trained on 5 voice samples

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React.js 18, React Router |
| Backend | Java Spring Boot 3, Spring Security |
| Authentication | JWT Tokens |
| ML Service | Python FastAPI, scikit-learn |
| Voice Processing | Librosa (MFCC extraction) |
| ML Model | Gaussian Mixture Model (GMM) |
| Database | MySQL 8 |
| ORM | Spring Data JPA / Hibernate |

---

## 🏗️ System Architecture

```
React.js Frontend
       ↓ HTTPS REST API
Spring Boot Backend (Port 8080)
       ↓ HTTP
Python ML Service (Port 8000)
       ↓
MySQL Database (Port 3306)
```

**Voice Authentication Flow:**
1. User records voice (4 seconds) in browser
2. Audio sent to Spring Boot via REST API
3. Spring Boot forwards to Python ML service
4. Python extracts MFCC features → runs GMM model
5. Returns confidence score (0.0 to 1.0)
6. If score ≥ 0.60 → JWT issued → Dashboard access

---

## 📁 Project Structure

```
voice-auth-healthcare/
├── frontend/                    ← React.js
│   └── src/
│       ├── components/Auth/     ← Login, Register, Enroll
│       ├── components/Dashboard/← Doctor, Nurse, Admin views
│       ├── components/Patient/  ← Patient record view
│       ├── context/             ← Auth state management
│       └── services/            ← API calls
├── backend/                     ← Spring Boot
│   └── src/main/java/com/voiceauth/
│       ├── controller/          ← REST endpoints
│       ├── service/             ← Business logic
│       ├── model/               ← JPA entities
│       ├── repository/          ← Data access
│       └── security/            ← JWT + Spring Security
├── ml-service/                  ← Python FastAPI
│   ├── main.py                  ← API entry point
│   ├── enroll.py                ← Voice enrollment
│   ├── verify.py                ← Voice verification
│   └── voice_processor.py       ← MFCC extraction
└── database.sql                 ← MySQL schema + sample data
```

---
---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register new user |
| POST | `/api/auth/enroll-voice` | Upload voice sample (×5) |
| POST | `/api/auth/login` | Voice authentication login |
| GET | `/api/patients` | Get all patients |
| GET | `/api/patients/{id}` | Get patient by ID |
| POST | `/api/patients` | Create patient record |
| GET | `/api/audit/logs` | Get audit logs (Admin) |

---

## 🗄️ Database Schema

```
users          → id, full_name, email, role, department, is_locked
voice_prints   → user_id, model_path, is_enrolled, sample_count
patients       → patient_code, full_name, diagnosis, treatment_notes
audit_logs     → user_id, action, confidence, status, timestamp
auth_sessions  → user_id, jwt_token, expires_at
```

---

## 🏆 Achievements

- 🥇 **1st Place — Nan Mudhalvan Hackathon** for this project
- Demonstrated expertise in voice recognition, authentication security, and healthcare technology

---
---

## 👨‍💻 Author

**Harjith K** — Aspiring Software Developer
- GitHub: [@Harjith2004](https://github.com/Harjith2004)
- LinkedIn: [harjith-k-839a55354](https://www.linkedin.com/in/harjith-k-839a55354)
- Email: harjithharjith40711@gmail.com

---

> ⭐ Star this repo if you found it useful!
