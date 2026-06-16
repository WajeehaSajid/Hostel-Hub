
<div align="center">

# HostelHub

A full-stack hostel management platform for university students and administrators.

[![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)](https://nextjs.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://postgresql.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://typescriptlang.org)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)

</div>

---

## Overview

HostelHub is a role-based platform where students and admins interact through a unified dashboard. Students can browse the marketplace, submit maintenance tickets, join community discussions, track lost items, view events, and receive notifications. Admins manage users, platform settings, and monitor all activity.

---

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| Frontend | Next.js 14, TypeScript, Tailwind CSS, Framer Motion |
| Backend | FastAPI, Python 3.11, psycopg3, connection pooling |
| Database | PostgreSQL |
| Auth | JWT (python-jose), bcrypt password hashing |

---

## Features

| Module | Description |
|--------|-------------|
| Authentication | Role-based login for students and admins with JWT |
| Marketplace | Buy and sell items within the hostel community |
| Maintenance | Submit and track maintenance requests |
| Events | View and manage hostel events |
| Lost & Found | Report and search for lost items |
| Community | Discussion board for hostel residents |
| Safety Alerts | Post and view safety-related announcements |
| Polls | Create and vote on community polls |
| Guidebook | Hostel rules, FAQs, and resources |
| Notifications | Real-time notification system |
| Admin Panel | User management, settings, and maintenance mode |

---

## Project Structure

```
hostel-hub/
├── app/                        # Next.js app directory
│   ├── page.tsx
│   ├── layout.tsx
│   └── globals.css
├── components/
│   ├── auth/                   # Login form
│   └── dashboard/              # All dashboard views
├── backend/
│   ├── main.py                 # FastAPI entry point
│   ├── auth/                   # Authentication logic
│   ├── core/                   # Config and settings
│   ├── database/               # DB connection pool
│   └── modules/                # Feature modules
│       ├── marketplace/
│       ├── maintenance/
│       ├── events/
│       ├── lost_found/
│       ├── community/
│       ├── notifications/
│       ├── polls/
│       ├── safety_alerts/
│       ├── guidebook/
│       ├── settings/
│       └── users/
├── .env.example
└── README.md
```

---

## Getting Started

### Prerequisites

- Node.js 18+
- Python 3.11+
- PostgreSQL

### Backend Setup

```bash
cd backend
pip install -r requirements.txt
```

Create a `.env` file inside the `backend/` folder:

```env
DATABASE_URL=postgresql://postgres:password@localhost:5432/hostelhub
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=1440
REFRESH_TOKEN_EXPIRE_DAYS=30
```

Run the backend server:

```bash
uvicorn main:app --reload
```

Backend runs at `http://localhost:8000`
Interactive API docs at `http://localhost:8000/docs`

---

### Frontend Setup

```bash
npm install
```

Create a `.env.local` file in the root folder:

```env
NEXT_PUBLIC_API_URL=http://localhost:8000
```

Run the frontend:

```bash
npm run dev
```

Frontend runs at `http://localhost:3000`

---

## API Reference

| Module | Base Route |
|--------|-----------|
| Auth | `/api/v1/auth` |
| Users | `/api/v1/users` |
| Marketplace | `/api/v1/marketplace` |
| Maintenance | `/api/v1/maintenance` |
| Events | `/api/v1/events` |
| Lost & Found | `/api/v1/lost-found` |
| Community | `/api/v1/community` |
| Notifications | `/api/v1/notifications` |
| Polls | `/api/v1/polls` |
| Safety Alerts | `/api/v1/safety-alerts` |
| Guidebook | `/api/v1/guidebook` |
| Settings | `/api/v1/settings` |

---

## Environment Variables

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `SECRET_KEY` | JWT signing secret — change in production |
| `ALGORITHM` | JWT signing algorithm (HS256) |
| `ACCESS_TOKEN_EXPIRE_MINUTES` | Access token lifetime |
| `REFRESH_TOKEN_EXPIRE_DAYS` | Refresh token lifetime |
| `NEXT_PUBLIC_API_URL` | Backend API URL used by the frontend |

---

## Notes

- Never commit `.env` or `.env.local` — both are listed in `.gitignore`
- Use `.env.example` as a reference when setting up the project
- All API responses follow a consistent format: `{ success, data, message }`
