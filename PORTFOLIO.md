# Evently — Full-Stack Event Discovery & Ticketing Platform

A production-deployed, full-stack web application for discovering, publishing, and booking event tickets, built end-to-end (backend, frontend, payments, and cloud infrastructure) as a solo project.


## Highlights

- Full ticketing flow with real **Stripe Checkout** integration (test mode) for paid events, and instant booking for free events
- JWT authentication with **role-based access control** (User/Admin), including a full admin dashboard (platform stats, event/user/booking management)
- Bilingual UI (Arabic/English) with instant **RTL/LTR** layout switching via i18next
- Full search & filtering (text, category, location, date range, price range, sorting) with server-side pagination
- Deployed across three cloud providers with a **Dockerized** API, environment-based configuration, and CORS/secrets properly separated from source control

## Tech Stack

**Backend** — ASP.NET Core 10 Web API · Entity Framework Core · PostgreSQL · JWT Auth · BCrypt · Stripe.NET · Swagger/OpenAPI

**Frontend** — React 19 · TypeScript · Vite · Tailwind CSS · React Router · react-i18next · Axios

**Infrastructure & DevOps** — Docker · Neon (serverless Postgres) · Render (containerized API hosting) · Vercel (frontend hosting/CI) · Git/GitHub

## Key Engineering Details

- Transactional booking logic preventing overselling of tickets, with automatic ticket-count restoration on cancellation
- Stripe checkout flow using session verification + idempotency guard against duplicate bookings
- Resolved a production container crash caused by inotify-watcher exhaustion in constrained cloud environments
- Config-driven CORS/environment setup enabling clean promotion across local → staging → production
