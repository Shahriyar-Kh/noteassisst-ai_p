<!-- ================= PREMIUM ANIMATED HEADER ================= -->

<h1 align="center">🚀 NoteAssist AI</h1>
<h3 align="center">Enterprise AI Study Platform • Django • DRF • React</h3>

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=24&duration=3000&pause=1000&color=00F7FF&center=true&vCenter=true&width=700&lines=AI-Powered+Note+Taking+Platform;Full-Stack+Django+%2B+React+Application;Scalable+REST+API+Architecture;Production-Ready+Learning+System" />
</p>

---

<p align="center">
<img src="https://img.shields.io/badge/Python-3.9%2B-blue" />
<img src="https://img.shields.io/badge/Django-4.2-green" />
<img src="https://img.shields.io/badge/DRF-REST%20API-red" />
<img src="https://img.shields.io/badge/React-18-blue" />
<img src="https://img.shields.io/badge/PostgreSQL-Supabase-informational" />
<img src="https://img.shields.io/badge/Redis-Caching-critical" />
<img src="https://img.shields.io/badge/Celery-Async-success" />
<img src="https://img.shields.io/badge/Status-Production%20Ready-brightgreen" />
</p>

---

## 🔍 SEO Keywords

> AI Study Platform, Django REST API, React Learning App, Full Stack Python Project, AI Note Generator, Scalable Django Backend, Production Ready AI Application

---

## 📖 Overview

**NoteAssist AI** is a full‑stack, enterprise‑grade AI study platform designed to help students and professionals generate, organize, and optimize learning content using AI. The project demonstrates production-ready backend architecture, secure API design, and a modern React frontend.

---

## 🚀 Why This Project Matters

- 📚 Reduces manual study effort through AI-assisted summaries and topic generation.
- ⚡ Demonstrates scalable Django REST architecture with async processing and caching.
- 🧠 Integrates practical AI features for real-world learning workflows.
- 🏗️ Production‑ready design suitable for evaluation by engineering and product teams.

---

## ✨ Key Features

- Full REST API for notes, users, AI tools, and admin operations (Django + DRF).
- React + Vite frontend with Tailwind CSS for responsive UX.
- AI toolset: summarize, generate topics, improve content, generate code snippets, and code execution support.
- Google OAuth + Google Drive integration with secure token handling.
- Role-based admin dashboard with user management and action logs.
- Background processing via Celery; Redis for caching and fast lookups.
- Production deployment: Render (backend) + Vercel (frontend) + Supabase (Postgres).

---

## 🧠 AI Capabilities

- Level-based summarization (beginner → expert) with length controls.
- Context-aware topic generation and content improvement.
- Code generation and sandboxed execution service.
- Usage tracking and quota enforcement per user plan.

---

## 📊 Architecture Diagram

<p align="center">
<img src="./NoteAssiss-AI_Architecture - Copy (2).png" width="700" alt="NoteAssist AI architecture diagram" />
</p>

---

## 🏗️ System Architecture

Client: React (Vite) SPA — Vercel

API: Django + Django REST Framework — Render

Persistence & infra: PostgreSQL (Supabase), Redis (cache/broker), Celery workers

High-level flow:
1. Frontend requests AI operation → API
2. API enqueues Celery task
3. Celery worker processes AI, stores results in Postgres + Redis
4. Frontend polls or receives status updates

---

## 🛠️ Tech Stack

- Backend: Python, Django, Django REST Framework, djangorestframework-simplejwt
- Frontend: React, Vite, Tailwind CSS, Redux
- Async & Queue: Celery, Redis
- Database: PostgreSQL (Supabase)
- Auth: Google OAuth, JWT
- Hosting: Vercel, Render
- Testing: Pytest

---

## 📊 Key Technical Achievements

- Designed for scale: architecture supports 10,000+ concurrent users with optimized queries and caching.
- Performance tuning: typical optimized note-list endpoints <50ms.
- Secure integrations: Google OAuth, JWT, env-driven secret management.
- Production deployment patterns: automated migrations, static asset collection, and worker orchestration.

---

## 🔐 Security & Performance

- JWT-based authentication and role-based authorization.
- Redis caching and cache invalidation strategies for expensive AI outputs.
- Query optimization (select_related/prefetch) to avoid N+1 queries.
- Rate limiting and request deduplication for AI endpoints.
- Recommended: HTTPS, strict CORS, monitoring for Celery workers.

---

## 📦 Project Structure (high level)

- `NoteAssist_AI_Backend/` — Django project (settings, wsgi, asgi, celery)
  - `accounts/`, `notes/`, `ai_tools/`, `dashboard/`, `utils/`
- `NoteAssist_AI_frontend/` — React + Vite app (`src/components`, `src/pages`, `src/services`)
- `docs/` — deployment and architecture guides

---

## 📸 Screenshots

> (Placeholder — add application screenshots here)

---

## ⚙️ Installation & Setup (Local Development)

Prerequisites: Python 3.9+, Node 18+, npm/yarn, PostgreSQL (or Supabase), Redis.

Backend (PowerShell example)
```powershell
cd "D:\Django Projects\NoteAssist_AI\NoteAssist_AI_Backend"
python -m venv ../env
& "../env/Scripts/Activate.ps1"
pip install -r requirements.txt
copy .env.example .env
# Edit .env with DATABASE_URL, SECRET_KEY, etc.
python manage.py migrate
python manage.py collectstatic --noinput
python manage.py runserver
```

Frontend
```bash
cd "D:\Django Projects\NoteAssist_AI\NoteAssist_AI_frontend"
npm install
cp .env.example .env
# Set VITE_API_BASE_URL=http://localhost:8000
npm run dev
```

Run tests (backend)
```bash
cd NoteAssist_AI_Backend
pytest
```

---

## 🌐 Live Demo

- Frontend: https://noteassistai.vercel.app
- API: https://noteassist-ai.onrender.com/api/

---

## 📡 API Overview (Selected Endpoints)

- `POST /api/auth/login/` — obtain JWT tokens
- `POST /api/auth/refresh/` — refresh token
- `GET /api/notes/` — list notes (paginated)
- `POST /api/notes/` — create note
- `POST /api/ai_tools/generate_topic/` — request AI topic generation (async)

Authentication: Bearer token (JWT). Admin routes require elevated permissions.

---

## 🚀 Deployment (Production)

Recommended providers:
- Frontend: Vercel
- Backend: Render
- Database: Supabase (managed Postgres)
- Cache & Broker: Redis

Environment variables (example):
- `ENVIRONMENT=production`, `DEBUG=False`, `SECRET_KEY`, `DATABASE_URL`, `REDIS_URL`, `GOOGLE_OAUTH_CLIENT_ID/SECRET`

Deployment summary:
1. Push `main` to GitHub.
2. Connect repo to Render and Vercel.
3. Configure environment variables.
4. Ensure migrations and `collectstatic` run during build.
5. Start Celery workers.

---

## 🧪 Future Enhancements

- Enterprise SSO (SAML/OIDC).
- Real-time collaboration and WebSocket updates.
- Model-agnostic AI provider adapters and prompt tuning.
- Multi-tenant support and per-tenant rate limits.

---

## 🤝 Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/your-feature`.
3. Add tests and documentation.
4. Open a PR with a clear description.

Code style: backend follows PEP8 and Django best practices; frontend follows existing React + Tailwind conventions.

---

## 👨‍💻 Author

Shahriyar Khan — Maintainer & Architect

---

⭐ Star the repo if you find it useful

