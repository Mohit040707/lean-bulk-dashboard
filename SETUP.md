# Lean Bulk Dashboard v2

## 1. Run locally
Install Node.js, then in this folder:

```bash
npm install
npm run dev
```
Open the localhost URL Vite shows.

## 2. Optional Supabase cloud login
The app works locally without Supabase using browser storage. For cloud login/sync, create a Supabase project and copy `.env.example` to `.env`, then add:

- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_ANON_KEY`

The current starter includes magic-link login scaffolding. A production sync layer should add authenticated database tables/RLS for task completion and weight logs.

## 3. Deploy on Vercel
Push this folder to GitHub, import the repo into Vercel, set the two `VITE_SUPABASE_*` environment variables if using Supabase, and deploy.
