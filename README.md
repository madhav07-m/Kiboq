# Kiboq — Intelligent Taskspace

A full-stack, AI-powered Kanban board for real-time team collaboration — built with the PERN stack (PostgreSQL, Express, React, Node.js), Tailwind CSS v4, and Google Gemini.

Describe a goal in one line and AI turns it into a fully prioritized backlog, breaks big tasks into subtasks, and summarizes your sprint progress — while your whole team collaborates on the board in real time with live drag-and-drop, presence, and instant updates over Socket.IO.

## Features

- **User Authentication** — Secure register & login with JWT and bcrypt password hashing, protected routes, and auto-login on refresh
- **Boards Management** — Create, rename, recolor and delete boards, with "my boards" and "shared with you" views and live per-board task counts
- **Kanban Board (Drag & Drop)** — Move task cards across columns with `dnd-kit`, order and column persisted to the database
- **Columns** — Add, rename, reorder and delete columns per board, with position-based ordering
- **Tasks** — Full CRUD with title, description, priority, due date, and assignee, opened in a rich task modal
- **Board Sharing & Members** — Invite teammates by search, assign owner/admin/member roles, and share or unshare a board in one click
- **Real-Time Collaboration** — Socket.IO syncs every move, edit and add instantly across all connected teammates, with live presence avatars
- **AI Task Generation** — Describe a goal and Google Gemini returns a full, prioritized backlog of tasks ready to drop onto the board
- **AI Task Breakdown** — Turn any big task into a clean list of actionable subtasks with one click
- **AI Sprint Summary** — Gemini reads the whole board and returns a concise, human-readable summary of progress and what's left
- **Dashboard Analytics** — KPI cards for boards and tasks, board-workload analytics, and a recent-activity feed from a single aggregation endpoint
- **My Tasks, Calendar & Team** — A cross-board task list biased to you, a due-date calendar, and a team directory — all from real data
- **Multi-Tenant Ready** — Every board, column and task is owner/member-scoped, so users only ever see data they're part of
- **Premium Responsive UI** — React 19, Tailwind v4 with custom theme tokens, framer-motion animations, a hand-built shadcn-style component kit, and a clean forest-green dashboard

## Tech Stack

**Frontend:** React 19, Tailwind CSS v4, Framer Motion, `@dnd-kit`, Socket.IO Client

**Backend:** Node.js, Express, PostgreSQL (Neon), Socket.IO, JWT, bcrypt

**AI:** Google Gemini (task generation, task breakdown, sprint summaries)

**Architecture:** Modular routes → controllers → services, raw SQL with `pg` (no ORM), centralized error handling, and an all-or-nothing transactional seed script

## Getting Started

### Prerequisites

- Node.js (v18+)
- PostgreSQL database (e.g. [Neon](https://neon.tech))
- Google Gemini API key

### Installation

```bash
# Clone the repository
git clone https://github.com/madhav07-m/Kiboq.git
cd Kiboq

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

### Environment Variables

Create a `.env` file in the `backend` directory:

```env
DATABASE_URL=your_postgres_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
PORT=5000
```

### Database Setup

Run the seed script to set up demo data:

```bash
cd backend/src/db
node seed.js
```

### Running Locally

```bash
# Start the backend
cd backend
npm run dev

# Start the frontend (in a separate terminal)
cd frontend
npm run dev
```

The app will be available at `http://localhost:5173`.

## Demo Login

```
Email: madhav@example.com
Password: Test@1234
```

## License

This project is for educational/portfolio purposes.
