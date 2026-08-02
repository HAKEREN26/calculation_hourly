# Hakeren — Hourly Worker Rights Calculation Form

Worker rights calculation form for **hourly-paid** foreign workers in Israel.
Companion to the monthly-salary form (repo: `calculation`).

## Routes

- `/calculation` — Hourly worker calculation form (public, after payment)

## Key differences from the monthly form

- Collects **hourly wage** data (hours/day, days/week, wage/hour) instead of monthly salary
- Wage updates capture the full hours/days/rate snapshot per change
- Adds **employer name** field
- Adds **work type** (Cleaning / House Keeping / Other)
- Adds **employer vacations** section (in addition to employee vacations)
- Recuperation / annual leave / holidays are Yes-No questions with a conditional date
- No passport photo upload

## Deploy

Deployed via Vercel. Connected to this GitHub repo.
Any push to `main` → auto-deploy.

## Tech Stack

- Next.js 14
- React 18
- Deployed on Vercel

## Backend

Submissions are POSTed to a Make.com webhook (`WEBHOOK_URL` in `page.jsx`).
The payload carries `formType: "hourly"` so a shared Make router can tell the
hourly and monthly forms apart.
