# 🔐 BiltyVault v1.0

> AI-powered bilty management system for Pakistani logistics businesses — image scanning, real-time tracking, and multi-user access in one secure web app.

---

## ✨ Features

- 🔐 **Password Login** — secure shared access for your team
- 📸 **AI Image Scanning** — Gemini AI reads bilty photos automatically
- ✏️ **Manual Entry** — type data yourself when needed
- 📊 **Live Dashboard** — total, pending, today's shipment count
- 🔍 **Search & Filter** — by bilty number, city, status
- 📱 **Mobile First** — works on phone, tablet, and desktop
- 🗄️ **PostgreSQL** — handles 100+ concurrent users safely
- 🛡️ **Production Secure** — Helmet, rate limiting, session auth

---

## 🚀 Deploy on Railway (Free — 20 Minutes)

### Step 1 — Upload to GitHub
Fork this repo or upload all files to your own GitHub repository.

### Step 2 — Deploy on Railway
1. Go to [railway.app](https://railway.app) and login with GitHub
2. Click **New Project** → **Deploy from GitHub repo**
3. Select your repository

### Step 3 — Add PostgreSQL Database
In Railway dashboard → **+ New** → **Database** → **PostgreSQL**
`DATABASE_URL` will be set automatically ✅

### Step 4 — Set Environment Variables
In Railway → your app → **Variables** tab:

| Variable | Value |
|----------|-------|
| `APP_PASSWORD` | your chosen password |
| `SESSION_SECRET` | any random 40+ character string |
| `GEMINI_API_KEY` | from aistudio.google.com (free) |
| `NODE_ENV` | `production` |
| `PORT` | `3000` |

### Step 5 — Done! 🎉
Your live HTTPS URL will be ready. Share with your team.

---

## 💻 Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/your-username/biltyvault.git
cd biltyvault

# 2. Install dependencies
npm install

# 3. Create environment file
cp .env.example .env
# Open .env and fill in your values

# 4. Start server
node server.js

# 5. Open in browser
# http://localhost:3000
```

---

## 📁 Project Structure

```
biltyvault/
├── server.js              ← Express backend (Auth, API, AI, DB)
├── package.json           ← All dependencies
├── ecosystem.config.js    ← PM2 production config
├── .env.example           ← Copy this to .env
├── .gitignore             ← Keeps secrets out of GitHub
└── public/
    └── index.html         ← Complete frontend (Login + App)
```

---

## 🔑 Get Your Free Gemini API Key

1. Visit [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Click **Create API Key**
3. Copy and paste into Railway Variables as `GEMINI_API_KEY`

Free tier: ~1,500 requests/day — enough for 100 daily users.

---

## 🛡️ Security

| Protection | Detail |
|-----------|--------|
| Password Auth | Shared login for your team |
| PostgreSQL Sessions | Server-side, 8hr expiry |
| Session Regeneration | Prevents session fixation |
| Login Rate Limit | 10 attempts per 15 minutes |
| AI Rate Limit | 15 requests per minute |
| General Rate Limit | 300 requests per 15 minutes |
| Helmet.js | 12 HTTP security headers |
| Parameterized Queries | No SQL injection possible |
| Memory-only Uploads | Images never written to disk |

---

## 📊 Capacity

| Users | Status |
|-------|--------|
| 1 – 15 | ✅ Works perfectly |
| 15 – 100 | ✅ Works perfectly |
| 100 – 500 | ✅ Increase PM2 instances |

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Node.js + Express |
| Database | PostgreSQL |
| AI | Google Gemini 1.5 Flash |
| Auth | express-session + connect-pg-simple |
| Security | Helmet + express-rate-limit |
| File Upload | Multer (memory only) |
| Frontend | Vanilla HTML / CSS / JavaScript |

---

## 📝 License

MIT — free to use, modify, and deploy.
