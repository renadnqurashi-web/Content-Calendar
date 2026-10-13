# MY NAGHI Content Calendar

Monthly TikTok and Instagram plans with a daily post and story, bilingual caption suggestions, manager approvals, English/Arabic interface.

Netlify project: **mynaghi-content-calendar** (already created, passcodes already set)
Live address after deploy: https://mynaghi-content-calendar.netlify.app

## Deploy (same way as the Content Hub)

1. Create a new GitHub repository, for example `mynaghi-content-calendar`, and upload everything in this folder (keep the `netlify` and `public` folders as they are).
2. In Netlify, open **mynaghi-content-calendar** → **Project configuration → Build & deploy → Link repository**, and pick that repository. Netlify reads `netlify.toml`, so leave the build settings as they are.
3. Add your Claude API key: **Project configuration → Environment variables → Add a variable**
   - Key: `ANTHROPIC_API_KEY`
   - Value: your key from console.anthropic.com (the same one the Content Hub uses is fine)
   - Scope: Functions
4. Trigger a deploy (**Deploys → Trigger deploy**).

## Sign-in

Everyone signs in with their name and a passcode.

| Variable | Who uses it |
|---|---|
| `TEAM_PASSCODE` | Everyone: plan, write captions, send for approval |
| `MANAGER_PASSCODE` | Managers only: approve or send back ideas |

Change either one in Netlify's environment variables, then redeploy.

## What's in this folder

- `public/index.html` — the website
- `netlify/functions/store.mjs` — shared storage for plans and approvals (Netlify Blobs); approvals need the manager passcode
- `netlify/functions/generate.mjs` — AI caption suggestions through your Claude API key
- `netlify.toml`, `package.json` — Netlify settings

Scheduling to Metricool works in the Claude version of the planner; on this website the team copies captions into Metricool.
