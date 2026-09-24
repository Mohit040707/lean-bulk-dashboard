# Lean Bulk Dashboard V2 — Supabase setup

## 1. Local setup
npm install
npm run dev

## 2. Supabase
The database tables and RLS policies are created by the SQL supplied in chat.

In Supabase, go to **Project Settings → API** and copy:
- Project URL
- Publishable/anon public key (use the key intended for browser clients)

Create a local `.env` file from `.env.example`:

VITE_SUPABASE_URL=...
VITE_SUPABASE_ANON_KEY=...

Never put a Supabase service-role/secret key in this frontend.

## 3. Email login
The app uses Supabase magic-link email login. In Supabase go to **Authentication → URL Configuration** and add your deployed Vercel URL to the allowed redirect URLs, for example:

https://your-project.vercel.app

For local development also add:
http://localhost:5173

## 4. Vercel
In Vercel: Project → Settings → Environment Variables. Add:
VITE_SUPABASE_URL
VITE_SUPABASE_ANON_KEY

Apply them to Production (and Preview if desired), then redeploy.

The public browser key is expected to be exposed to the frontend. Do not expose a service-role/secret key.
