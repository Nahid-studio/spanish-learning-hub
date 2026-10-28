# Hola Habits — Spanish Learning Hub

A responsive, beginner-friendly Spanish study website built from your 30-day plan and its 300 phrase bank.

## Included
- 30-day plan with lesson and listening links (YouTube search links based on lesson titles)
- 300 Spanish phrases (10 per day) with English meanings, checkboxes, and text-to-speech playback
- Dashboard: completed days, practice minutes, phrases practised, quiz best, and current streak
- Daily 10-question quiz
- Speaking studio with Spanish speech playback, typed self-check, and optional browser speech recognition
- Achievements
- Local progress storage by default
- Optional cross-device sync with Supabase Auth + Postgres

## Try it locally
Because the site loads `data.json`, run it through a local web server instead of opening `index.html` directly.

### Easiest: Python
1. Install Python if you do not already have it.
2. Open a terminal in this folder.
3. Run `python -m http.server 8000`
4. Open `http://localhost:8000`

## Free online hosting
Use GitHub Pages, Netlify, or another static host. Upload all files in this folder to the host. No custom domain is required; you receive a free provider subdomain.

## Enable cross-device sync (Supabase free plan)
1. Create a project at https://supabase.com.
2. In the project dashboard, open SQL Editor and run the complete contents of `supabase-setup.sql`.
3. Open Project Settings / API and copy the Project URL and the publishable/anon public key.
4. Paste those values into `config.js`:
   - `SUPABASE_URL: "https://YOUR-PROJECT.supabase.co"`
   - `SUPABASE_ANON_KEY: "YOUR-PUBLISHABLE-OR-ANON-KEY"`
5. Deploy the updated folder again. In Supabase Auth settings, configure your site's URL and allowed redirect URLs for the address provided by your free host.
6. Use the account icon in the site to create an account, confirm your email if requested, and sign in on both devices.

### Security notes
- Only put the Supabase publishable/anon key in browser code. Never place a service-role or secret key in `config.js`.
- The SQL uses Row Level Security so users can access only the row whose `user_id` matches their signed-in account.
- Keep your account email and password private. Review Supabase's current free-plan limits before relying on it long-term.

## Progress data
Without Supabase configured, progress is saved only in that browser's local storage. It will not sync between devices and can be lost if browser site data is cleared. Cloud sync requires the setup above.
