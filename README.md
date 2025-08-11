# BusyBeez → Netlify Functions + Cronofy (Read-only)

Endpoints:
- `/api/connect?family=FAMILY_ID&user=USER_ID` → Redirects to Cronofy Hosted Connect
- `/api/callback` → Exchanges `code` for tokens (server-side)
- `/api/events?family=FAMILY_ID&tzid=America/Chicago` → Merged events JSON for your UI
- `morning-brief` (scheduled) → skeleton for daily AI summary

Deploy (web-only, no CLI):
1) Put these files in a NEW GitHub repo (root must contain `netlify.toml` and the `netlify/functions` folder).
2) Netlify → Add new site → Import from Git → Publish directory: `.` (a single dot). Build command: leave blank.
3) Add env vars (Site configuration → Environment variables) based on `.env.example`, then Trigger redeploy.
4) Test: `https://<your-site>.netlify.app/.netlify/functions/events?family=test&tzid=America/Chicago`
5) Connect a user: `https://<your-site>.netlify.app/.netlify/functions/connect?family=sharma&user=kota`

Security: Never commit real secrets. Tokens are stored server-side via Netlify Blobs by default.
