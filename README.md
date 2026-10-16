# BiltyVault

An AI-powered logistics app for managing bilty documents. You snap or upload a bilty, and the app reads the details automatically with Google's Gemini vision model, then stores everything in a database so records are easy to search and keep.

## Tech

- Node.js with Express
- PostgreSQL (via `pg`)
- Google Generative AI (Gemini) for reading bilty images
- Session-based login, with Helmet and rate limiting for basic security
- Multer for file uploads

## What is inside

- `server.js`, the Express server and API
- `public/`, the frontend
- `.env.example`, a template for the environment variables

## Configuration

Copy `.env.example` to `.env` and fill in real values for local development. Do not commit `.env`.

The variables are:

- `DATABASE_URL`, the PostgreSQL connection string (Railway injects this automatically when a Postgres service is linked)
- `SESSION_SECRET`, a strong random string used to sign session cookies
- `APP_PASSWORD`, the password users enter to log in
- `GEMINI_API_KEY`, the Google Generative AI key
- `NODE_ENV`, set to `production` on the server
- `PORT`, the port to listen on

## Running it locally

You need Node.js and a PostgreSQL database.

```
npm install
cp .env.example .env
# fill in .env, then:
npm run dev
```

`npm run dev` runs the server with nodemon so it restarts on changes. For a plain run, use `npm start`.

## Deployment

Deployed on Railway with a linked Postgres service. On Railway the environment variables are set in the dashboard, and `.env` is not used in production.

## Author

Saima Hamid, Ninja Tech, Lahore. https://ninjatechdev.com
