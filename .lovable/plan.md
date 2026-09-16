# Import "magic-accelerate-flow" into this project

Bring the full app from the public GitHub repository into this project so it runs here with its own backend.

## What the app is

An AI channel studio: you add YouTube sources, it analyses them, generates ideas, turns them into scripts, builds videos, and can schedule posts to channels.

Screens found in the repo:
- Sign-in page
- Sources (add and analyse YouTube links)
- Chat with an AI strategist
- Studio (scripts and video production)
- Channels (scheduling and posting)
- Overview page

## What gets set up

1. Copy all pages, components, styles and logic from the repository into this project, replacing the current blank home page.
2. Turn on Lovable Cloud (database, logins, file storage, server code).
3. Recreate the database exactly as in the repo: profiles, projects, sources, source videos, ideas, scripts, videos, channels, posts and the scheduler config, each with the same access rules, plus the private "media" storage area for video files.
4. Set up accounts and sign-in (email/password) with automatic profile creation on sign-up.
5. Wire up the AI features and the scheduled-publishing endpoint with its secret key.
6. Check the app builds and every page loads, and confirm a sign-in works.

## What I will need from you

- Any existing data from the original app (a CSV or JSON export). Without it the app starts empty — everything else still works.
- Publishing on a schedule only becomes live once the app is published.

## Technical notes

- Repo is already a TanStack Start + Lovable Cloud project, so it transfers as-is; TanStack package versions stay aligned with this project's template.
- Server keys used by the code: LOVABLE_API_KEY (AI gateway), LOVABLE_CRON_SECRET (+ previous), and the Cloud-provided Supabase URL / publishable / service-role values.
- Schema comes from the repo's single migration (`supabase/migrations/20260916020020_*.sql`), applied unchanged including GRANTs, RLS policies, triggers and storage policies.
- Public endpoint `api/public/hooks/scheduled-videos` is preserved and stays secret-verified.
- YouTube ingestion uses public endpoints only — no API key needed.
