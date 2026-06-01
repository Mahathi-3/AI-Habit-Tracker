# 🧠 AI Habit Tracker

A full-stack MERN habit tracking app powered by **Google Gemini AI** — track your daily habits, build streaks, and get personalised AI-generated insights, weekly reports, and streak recovery coaching.

**Live Demo → [ai-habit-tracker-mocha.vercel.app](https://ai-habit-tracker-mocha.vercel.app)**

---

## ✨ Features

- **Daily habit check-offs** — one-click logging with progress rings and real-time completion tracking
- **Streak tracking** — current and longest streaks calculated across a 90-day history
- **90-day heatmap** — visual activity heatmap similar to GitHub contributions
- **AI Weekly Report** — Gemini AI analyses your week and gives personalised, data-driven feedback
- **AI Habit Suggestions** — get personalised habit ideas based on your existing habits
- **Streak Recovery Coach** — when a long streak breaks, AI generates a gentle 3-day comeback plan
- **AI Chat (Stats page)** — ask natural language questions about your habit data
- **Morning Motivation** — daily AI-generated motivational message
- **Weekly grid view** — see completion across all habits for the entire week at a glance
- **Statistics & Charts** — bar charts, pie charts (by category), and weekly breakdowns with Recharts
- **Dark / Light mode** — full theme toggle persisted to local storage
- **Drag-and-drop** — reorder habits with @dnd-kit
- **Archive & Delete** — manage habits without losing history
- **JWT Authentication** — secure sign-up / login with bcrypt password hashing

---

## 🛠️ Tech Stack

### Frontend
| Tech | Purpose |
|---|---|
| React 19 | UI framework |
| Vite | Build tool & dev server |
| Tailwind CSS v4 | Styling |
| React Router v6 | Client-side routing |
| Axios | HTTP client |
| Recharts | Charts & visualisations |
| @dnd-kit | Drag-and-drop habit reordering |
| Lucide React | Icons |
| canvas-confetti | Celebration animations |

### Backend
| Tech | Purpose |
|---|---|
| Node.js + Express | REST API server |
| MongoDB + Mongoose | Database & ODM |
| Google Gemini AI (`@google/genai`) | AI features |
| JWT + bcryptjs | Authentication & password hashing |
| dotenv | Environment variable management |

---

## 📁 Project Structure

```
├── backend/
│   ├── config/          # MongoDB connection
│   ├── controllers/     # Route logic (auth, habits, logs, AI)
│   ├── middleware/      # Auth guard, error handler
│   ├── models/          # Mongoose schemas (User, Habit, HabitLog, AIInsight)
│   ├── routes/          # Express routers
│   ├── scripts/         # Seed script
│   ├── utils/           # Shared utilities
│   └── server.js        # Entry point
│
├── frontend/ai-habit-tracker-ui-boilerplate-code/
│   ├── src/
│   │   ├── api/         # Axios instance
│   │   ├── components/  # Reusable UI components
│   │   ├── context/     # Auth & Theme context
│   │   ├── pages/       # Dashboard, Habits, Stats, Weekly, Insights, Landing
│   │   └── utils/       # Date helpers, confetti, constants
│   └── index.html
│
├── .gitignore
└── vercel.json          # Vercel deployment config
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js ≥ 18
- MongoDB (local or [MongoDB Atlas](https://cloud.mongodb.com))
- A [Google Gemini API key](https://aistudio.google.com/app/apikey)

### 1. Clone the repository

```bash
git clone https://github.com/Mahathi-3/AI-Habit-Tracker.git
cd AI-Habit-Tracker
```

### 2. Set up the Backend

```bash
cd backend
npm install
```

Create a `.env` file inside `backend/`:

```env
PORT=8000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
GEMINI_API_KEY=your_gemini_api_key
CLIENT_URL=http://localhost:5173
```

Start the backend dev server:

```bash
npm run dev
```

### 3. Set up the Frontend

```bash
cd frontend/ai-habit-tracker-ui-boilerplate-code
npm install
```

Create a `.env` file inside the frontend folder:

```env
VITE_API_URL=http://localhost:8000/api
```

Start the frontend dev server:

```bash
npm run dev
```

Open **http://localhost:5173** in your browser.

---

## 🌐 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Register a new user |
| `POST` | `/api/auth/login` | Login and receive JWT |
| `GET` | `/api/habits` | Get all habits for the user |
| `POST` | `/api/habits` | Create a new habit |
| `PUT` | `/api/habits/:id` | Update a habit |
| `DELETE` | `/api/habits/:id` | Delete a habit |
| `PUT` | `/api/habits/:id/archive` | Toggle archive status |
| `POST` | `/api/logs` | Log a habit completion |
| `DELETE` | `/api/logs` | Remove a log entry |
| `GET` | `/api/logs/today` | Get today's completed habits |
| `GET` | `/api/logs/range` | Get logs for a date range |
| `GET` | `/api/logs/heatmap` | Get 90-day heatmap data |
| `POST` | `/api/ai/weekly-report` | Generate AI weekly report |
| `POST` | `/api/ai/suggest` | Get AI habit suggestions |
| `POST` | `/api/ai/recovery` | Get streak recovery plan |
| `POST` | `/api/ai/chat` | Chat with AI about your stats |
| `POST` | `/api/ai/motivation` | Get morning motivation message |
| `GET` | `/api/health` | Health check |

---

## ☁️ Deployment

### Frontend — Vercel
The `vercel.json` at the repo root configures Vercel to build from the correct subdirectory:
- **Root Directory:** `frontend/ai-habit-tracker-ui-boilerplate-code`
- **Build Command:** `npm run build`
- **Output Directory:** `dist`

Push to `main` and Vercel auto-deploys.

### Backend — Render / Railway
Deploy the `backend/` folder as a Node.js web service. Set all environment variables from your `.env` file in the platform dashboard. Set the start command to:

```bash
node server.js
```

---

## 📸 Pages

| Page | Description |
|---|---|
| **Landing** | Marketing page with feature showcase and animated orbit display |
| **Dashboard** | Today's habits, progress ring, AI weekly report, heatmap, weekly grid |
| **Habits** | Full list of all habits with drag-to-reorder |
| **Weekly** | Week-by-week completion grid |
| **Stats** | Bar charts, category pie chart, AI chat assistant |
| **Insights** | Deep AI-generated insights and patterns |

---

## 📄 License

MIT — feel free to use and build on this project.
