# ProgressPulse 🚀
## Smart Goal, Productivity & Task Tracking System

**ProgressPulse** is a modern MERN-stack based smart productivity ecosystem designed for students, professionals, fitness communities, and trainers. Unlike standard task management apps, ProgressPulse combines personal productivity tracking, academic competition, public challenges, real-time collaboration, and AI-generated motivation into one centralized platform.

**Vision:** *"To transform productivity tracking into a collaborative, intelligent, and motivating experience."*

---

## 🌟 Core Modes

ProgressPulse operates in three distinct, simultaneous modes accessible via a dashboard switcher:

### 1. Personal Productivity Mode (Private)
Manage your own habits, tasks, and goals with complete privacy.
*   **Task & Habit Tracking:** Categorize tasks, track streaks, and mark completions.
*   **Countdown Timers:** Track remaining days for exams, deadlines, or events.
*   **Analytics & Reports:** View weekly/monthly performance graphs (Chart.js) and export PDF summaries (jsPDF).
*   **AI Motivation:** Get personalized motivational quotes and weekly summaries powered by Llama 3.2.

### 2. Academic Competition Mode (Collaborative)
Build discipline through healthy competition and accountability.
*   **Group Creation:** Create or join private groups of 2-4 members using invite codes.
*   **Shared Challenges:** Admins can set study, coding, or workout goals that all members participate in equally.
*   **Real-Time Chat:** Coordinate and share updates via Socket.io powered private rooms.
*   **Leaderboards:** Compare productivity percentages and streak rankings.

### 3. Public Challenge Mode (Community Hub)
Join expert-created productivity programs.
*   **Verified Creators:** Teachers, gym trainers, and mentors can undergo admin verification to publish public challenges (e.g., "30-Day Coding Bootcamp" or "NEET Revision").
*   **Approval Workflow:** All challenges are vetted by Website Admins for safety and authenticity.
*   **Participant Tracking:** Users track their progress privately while contributing to a public participant leaderboard.

---

## 👥 User Roles
*   **Normal Users:** Manage personal tasks, join groups, and participate in public challenges.
*   **Group Admins:** Any user who creates a group. Can set shared challenges and manage members (but competes equally without editing privileges).
*   **Public Challenge Creators:** Verified professionals who curate public programs.
*   **Website Admin:** Manages platform security, verifies creators, and approves public challenges.

---

## 🛠️ Tech Stack
*   **Frontend:** React.js, Tailwind CSS, Chart.js, jsPDF, Socket.io-client
*   **Backend:** Node.js, Express.js, Socket.io
*   **Database:** MongoDB Atlas (Scalable & Dynamic)
*   **AI Integration:** Llama 3.2 3B via Ollama (with curated fallback quotes)
*   **Authentication:** JWT + bcrypt

---

## ⚡ Quick Start

### 1. Prerequisites
*   Node.js v18+ → https://nodejs.org
*   MongoDB Atlas account (already configured ✅)
*   Ollama (optional for AI) → https://ollama.ai

### 2. Clone / Extract Project
```bash
cd progresspulse

```

### 3. Install All Dependencies

```bash
# Install server dependencies
cd server && npm install

# Install client dependencies  
cd ../client && npm install

```

### 4. Create Admin Account

```bash
cd server && node createAdmin.js

```

This creates the default Website Admin:

* **Email:** admin@progresspulse.com
* **Password:** admin123

### 5. Start the App

**Terminal 1 — Backend:**

```bash
cd server
npm run dev

```

**Terminal 2 — Frontend:**

```bash
cd client
npm start

```

### 6. Open in Browser

```
http://localhost:3000

```

---

## 🤖 Optional: Enable AI Motivation (Ollama)

```bash
# Install Ollama from [https://ollama.ai](https://ollama.ai)
# Then pull the model:
ollama pull llama3.2:3b

# Start Ollama (runs on port 11434):
ollama serve

```

*Note: If Ollama is not running locally, the application will automatically fall back to a curated list of motivational quotes.*

---

## 🔑 Environment Variables (`server/.env`)

```env
MONGO_URI=mongodb+srv://naikomkar106_db_user:UatKsYqjJWVaM5Qz@cluster0.29eac6z.mongodb.net/progresspulse?appName=Cluster0
JWT_SECRET=progresspulse_secret_omkar_2024
PORT=5000
CLIENT_URL=http://localhost:3000

```

---

## 🗂️ Project Structure

```text
progresspulse/
├── server/
│   ├── models/          # MongoDB schemas (Users, Tasks, Groups, Challenges)
│   ├── routes/          # API endpoints
│   ├── middleware/      # JWT Auth & Role validation middleware
│   ├── socket/          # Socket.io real-time chat logic
│   ├── createAdmin.js   # Admin seeder script
│   └── index.js         # Server entry point
└── client/
    └── src/
        ├── components/  # Reusable UI (Sidebar, Topbar, Mode Switcher)
        ├── context/     # Global state (Auth, Theme)
        ├── pages/
        │   ├── Auth/      # Login, Register
        │   ├── Personal/  # Dashboard, Tasks, Habits, Analytics, Countdown
        │   ├── Academic/  # Groups, GroupDetail, Chat
        │   ├── Public/    # Challenges marketplace, ChallengeDetail
        │   └── Admin/     # Admin verification & moderation panel
        └── utils/       # Axios interceptors, helper functions

```

---

## 🔗 Core API Endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Authenticate and receive JWT |
| GET | `/api/tasks` | Fetch user's tasks/habits |
| POST | `/api/tasks` | Create a new personal task |
| GET | `/api/groups` | Fetch groups the user belongs to |
| POST | `/api/groups/join` | Join a group via invite code |
| GET | `/api/challenges/public` | Fetch all approved public challenges |
| GET | `/api/analytics/weekly` | Fetch data for Chart.js generation |
| GET | `/api/ai/motivation` | Fetch Ollama 3.2 generated quote |
| GET | `/api/admin/users` | (Admin Only) View registered users |

---

## 👤 Default Accounts

| Role | Email | Password |
| --- | --- | --- |
| Website Admin | admin@progresspulse.com | admin123 |

*Register any email via the UI to create a standard user account.*

---

**Built with ❤️ — ProgressPulse Smart Productivity Ecosystem**

```

