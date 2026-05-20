# My Day Dashboard

Your personal daily dashboard — built as a static web app.

## What's inside

```
myday-app/
├── public/
│   └── index.html          ← Your entire dashboard lives here
├── package.json
├── netlify.toml            ← Auto-deploy config for Netlify
├── .gitignore
└── README.md
```

## Running locally

```bash
npm install
npm run dev
```

Then open http://localhost:3000

## Deploying to Netlify (get a real URL)

### Option A — Drag and drop (easiest, 2 minutes)
1. Go to netlify.com → sign up free with Google
2. On the dashboard, drag the entire `myday-app` FOLDER onto the deploy zone
3. Netlify gives you a URL like https://my-day-nikita.netlify.app
4. Done — bookmark it

### Option B — GitHub (best for ongoing updates)
1. Push this folder to a GitHub repo (see GitHub instructions below)
2. In Netlify → New Site → Import from GitHub → select your repo
3. Set publish directory to: public
4. Deploy — every time you push to GitHub, Netlify auto-updates your live site

## Migrating to Claude Code

Claude Code is a terminal tool. Here's exactly how to use it with this project:

### Step 1 — Install Claude Code
```bash
npm install -g @anthropic-ai/claude-code
```

### Step 2 — Open your project in Claude Code
```bash
cd path/to/myday-app
claude
```

### Step 3 — Example commands to say to Claude Code

"Add a new section to the Finance tab for investment tracking"
"Make the gratitude section save to a database instead of localStorage"  
"Add dark mode toggle to the topbar"
"Connect the news section to a real RSS feed API"
"Add user authentication so I can log in"
"Move all the data from localStorage to a Supabase database"

Claude Code will read your index.html, understand the full codebase,
and make changes directly to the file.

## Upgrading from localStorage to a real database

Right now all data saves to your browser localStorage.
This means data only exists on one device.

To sync across devices (Mac + iPhone), upgrade to Supabase:

### Step 1 — Create free Supabase account
Go to supabase.com → New project

### Step 2 — Tell Claude Code to migrate
Open Claude Code in your project folder and say:

"Migrate all localStorage data in index.html to Supabase. 
Use these tables: todos, wellness, gratitude, events, 
athlo_tasks, expenses. Add login with email/password.
My Supabase URL is: [paste your URL]
My Supabase anon key is: [paste your key]"

Claude Code will rewrite the data layer automatically.

### Step 3 — Deploy updated version to Netlify
Push to GitHub → Netlify auto-deploys.

## Making updates with Claude Code

Any time you want to change something, open Claude Code and describe it:

"The finance tab needs a chart showing monthly spend over time"
"Add push notifications for my daily wellness reminder at 8am"
"Make the todo list drag-and-drop sortable"
"Add a search bar that searches across all sections"

## File structure if you want to split into multiple files later

When your index.html gets too large, ask Claude Code to split it:

"Refactor this single HTML file into a proper structure:
- src/index.html (shell)
- src/css/styles.css (all styles)
- src/js/app.js (main logic)
- src/js/finance.js (finance module)
- src/js/athlo.js (work module)
Keep everything working exactly the same."

