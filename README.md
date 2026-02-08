# 🎬 UPLIFTLY

> **AI-Powered Creator Platform for Video Content Analysis**

[![Made with FastAPI](https://img.shields.io/badge/FastAPI-0.109.0-009688?logo=fastapi)](https://fastapi.tiangolo.com)
[![Made with Next.js](https://img.shields.io/badge/Next.js-14.1.0-black?logo=next.js)](https://nextjs.org)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-336791?logo=postgresql)](https://postgresql.org)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker)](https://docker.com)

---

## 📋 Overview

UPLIFTLY is an intelligent web platform designed to help content creators analyze, optimize, and improve their video content before publishing. Using AI-powered analysis, creators receive actionable insights and improvement suggestions to maximize audience engagement.

## ✨ Features

- 🔐 **Secure Authentication** - JWT-based login with bcrypt password hashing
- 📊 **User Dashboard** - Personalized analytics and content management
- 🎥 **Video Upload** - Coming soon: Upload videos for AI analysis
- 🤖 **AI Analysis** - Coming soon: Automated content optimization suggestions

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js 14, React 18, TypeScript |
| Backend | Python 3.11, FastAPI, SQLAlchemy |
| Database | PostgreSQL 15 |
| Auth | JWT, bcrypt |
| DevOps | Docker, Docker Compose |

## 📁 Project Structure

```
PROCREATE/
├── backend/
│   ├── app/
│   │   ├── main.py           # FastAPI entry point
│   │   ├── config.py         # Configuration
│   │   ├── database.py       # Database connection
│   │   ├── models/           # SQLAlchemy models
│   │   ├── schemas/          # Pydantic schemas
│   │   ├── routes/           # API endpoints
│   │   └── services/         # Business logic
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/
│   ├── src/
│   │   ├── app/              # Next.js pages
│   │   └── services/         # API client
│   ├── package.json
│   └── Dockerfile
├── docker-compose.yml
├── requirements.md           # Project requirements
├── design.md                 # System design
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Docker & Docker Compose (recommended)
- Or: Node.js 20+, Python 3.11+, PostgreSQL 15+

### Option 1: Docker (Recommended)

```bash
# Clone and navigate to project
cd UPLIFTLY

# Start all services
docker-compose up --build

# Access the application
# Frontend: http://localhost:3000
# Backend API: http://localhost:8000
# API Docs: http://localhost:8000/docs
```

### Option 2: Local Development

#### Backend Setup

```bash
# Navigate to backend
cd PROCREATE/backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Create .env file
cp .env.example .env
# Edit .env with your database credentials

# Run the server
uvicorn app.main:app --reload --port 8000
```

#### Frontend Setup

```bash
# Navigate to frontend
cd PROCREATE/frontend

# Install dependencies
npm install

# Create environment file
echo "NEXT_PUBLIC_API_URL=http://localhost:8000" > .env.local

# Run development server
npm run dev
```

#### Database Setup

```bash
# Create PostgreSQL database
createdb procreate

# The tables will be created automatically when the backend starts
```

## 🔗 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/signup` | Register new user |
| `POST` | `/login` | Authenticate user |
| `GET` | `/dashboard` | Get user dashboard (protected) |
| `GET` | `/health` | Health check |
| `GET` | `/docs` | Swagger API documentation |

### Example API Usage

```bash
# Signup
curl -X POST http://localhost:8000/signup \
  -H "Content-Type: application/json" \
  -d '{"name": "John Doe", "email": "john@example.com", "password": "secure123"}'

# Login
curl -X POST http://localhost:8000/login \
  -H "Content-Type: application/json" \
  -d '{"email": "john@example.com", "password": "secure123"}'

# Dashboard (with token)
curl http://localhost:8000/dashboard \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

## 🔒 Environment Variables

### Backend

| Variable | Description | Default |
|----------|-------------|---------|
| `DATABASE_URL` | PostgreSQL connection string | `postgresql://postgres:postgres@localhost:5432/procreate` |
| `SECRET_KEY` | JWT signing key | Change in production! |
| `ALGORITHM` | JWT algorithm | `HS256` |
| `ACCESS_TOKEN_EXPIRE_MINUTES` | Token expiry | `30` |
| `CORS_ORIGINS` | Allowed origins | `["http://localhost:3000"]` |

### Frontend

| Variable | Description | Default |
|----------|-------------|---------|
| `NEXT_PUBLIC_API_URL` | Backend API URL | `http://localhost:8000` |

## 📖 Documentation

- [requirements.md](./requirements.md) - Project requirements and specifications
- [design.md](./design.md) - System architecture and design decisions
- [API Docs](http://localhost:8000/docs) - Interactive Swagger documentation

## 🧪 Testing

```bash
# Backend tests (when implemented)
cd backend
pytest

# Frontend tests (when implemented)
cd frontend
npm test
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is developed for hackathon demonstration purposes.

---

<div align="center">
  <strong>Built with ❤️ for Hackathon 2026</strong>
</div>
