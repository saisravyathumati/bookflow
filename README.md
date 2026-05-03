# BookFlow — Multi-Tenant Booking System

BookFlow is a production-grade, multi-tenant appointment booking platform designed for service-based businesses (salons, clinics, etc.).

This system focuses on **correctness, scalability, and real-world reliability**, solving critical problems like double-booking, async notifications, and intelligent reminders.

---

## 🚀 Core Features

### 🧠 Smart Booking Engine

* Dynamic slot generation based on operating hours
* Real-time slot locking using DB transactions (`SELECT FOR UPDATE`)
* Prevents double bookings under concurrent requests

### 🏢 Multi-Tenant Architecture

* Tenant isolation using slug-based routing
* Shared infrastructure with strict data separation
* Scalable design for multiple businesses

### 🔔 Async Notifications (Celery + Redis)

* Booking confirmation messages
* Scheduled reminders (24h & 1h before appointment)
* Retry mechanism for failed deliveries
* Failure tracking and recovery

### 🤖 AI-Powered Reminders

* Personalized reminder generation using LLMs
* Context-aware messages (service, time, business)
* Fallback templates for reliability
* Admin override support

### 📅 Admin Booking Management

* View, cancel, reschedule bookings
* Manual booking creation
* Status tracking (completed, no-show, cancelled)

---

## 🏗️ Tech Stack

### Backend

* FastAPI (async APIs)
* PostgreSQL (transactional database)
* SQLAlchemy (ORM)

### Async Processing

* Celery (background jobs)
* Redis (message broker + result backend)

### AI Integration

* LLM-based reminder generation (fallback-first design)

### DevOps

* Docker & Docker Compose
* GitHub Actions (CI/CD)

---

## 📂 Project Structure

```
bookflow/
├── app/
│   ├── api/              # API routes
│   ├── services/         # Business logic
│   ├── repositories/     # DB access layer
│   ├── middleware/       # Tenant handling
│   ├── workers/          # Celery tasks
│   ├── ai/               # AI integrations
│   └── db/               # DB setup
├── tests/                # Unit & integration tests
├── docs/                 # API contracts
├── docker-compose.yml
└── README.md
```

---

## ⚙️ Getting Started

### 1. Clone the repo

```
git clone <your-repo-url>
cd bookflow
```

### 2. Run with Docker

```
docker-compose up --build
```

### 3. Access services

* API → http://localhost:8000
* Docs → http://localhost:8000/docs

---

## 🧪 Testing

```
pytest
```

Focus areas:

* Slot locking (concurrency)
* Booking creation
* Tenant isolation

---

## ⚠️ Design Principles

* **Correctness > Features**
* **Async-first architecture**
* **Fallback-first AI design**
* **Never trust frontend for access control**
* **Handle failure as a first-class concern**

---

## 🔥 Why This Project?

Most booking systems fail under:

* concurrent bookings
* unreliable notifications
* poor multi-tenant design

BookFlow is built to handle these **real-world production challenges** from day one.

---

## 👨‍💻 Author

Built as part of a full-stack system design project focusing on backend architecture, distributed systems, and production reliability.

---

## 📌 Roadmap

* Chat-to-book (LLM-powered booking assistant)
* Advanced analytics dashboard
* Payment integration
* Multi-channel notifications

---
