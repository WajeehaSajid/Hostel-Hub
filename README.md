# HostelHub

A full-stack hostel management platform built for university students and administrators.
Students can access marketplace listings, submit maintenance tickets, view events, report lost and found items, participate in community discussions, and receive notifications — all from a single dashboard.
Administrators have a separate view for managing users, settings, and monitoring platform activity.

---

## Tech Stack

**Frontend**
- Next.js (TypeScript)
- Tailwind CSS
- Framer Motion

**Backend**
- FastAPI (Python)
- PostgreSQL
- JWT Authentication (python-jose)
- psycopg3 with connection pooling

---

## Features

- Student and admin role-based authentication
- Marketplace — buy and sell items within the hostel
- Maintenance ticket submission and tracking
- Events — view and manage hostel events
- Lost and Found reporting
- Community discussion board
- Safety alerts
- Polls
- Guidebook
- Notifications system
- Admin dashboard with settings and maintenance mode

---

## Project Structure

```
hostel-hub/
├── app/                   # Next.js app directory
│   ├── page.tsx
│   ├── layout.tsx
│   └── globals.css
├── components/            # React components
│   ├── auth/
│   └── dashboard/
├── backend/               # FastAPI backend
│   ├── main.py
│   ├── auth/
│   ├── core/
│   ├── database/
│   └── modules/
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

Create a `.env` file in the `backend/` folder:

```
DATABASE_URL=postgresql://postgres:password@localhost:5432/hostelhub
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=1440
REFRESH_TOKEN_EXPIRE_DAYS=30
```

Run the backend:

```bash
uvicorn main:app --reload
```

Backend runs at `http://localhost:8000`

### Frontend Setup

```bash
npm install
```

Create a `.env.local` file in the root folder:

```
NEXT_PUBLIC_API_URL=http://localhost:8000
```

Run the frontend:

```bash
npm run dev
```

Frontend runs at `http://localhost:3000`

---

## API Overview

| Module | Prefix |
|--------|--------|
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

Full API docs available at `http://localhost:8000/docs` after running the backend.

---

## Environment Variables

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `SECRET_KEY` | JWT signing secret |
| `ALGORITHM` | JWT algorithm (HS256) |
| `ACCESS_TOKEN_EXPIRE_MINUTES` | Access token expiry |
| `REFRESH_TOKEN_EXPIRE_DAYS` | Refresh token expiry |
| `NEXT_PUBLIC_API_URL` | Backend API URL for frontend |

---

## Notes

- Never commit `.env` or `.env.local` files — they are listed in `.gitignore`
- Use `.env.example` as a reference for required environment variables
