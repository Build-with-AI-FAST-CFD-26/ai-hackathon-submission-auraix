# SyncGuard

> AI-powered decision conflict catcher for co-founding teams
> Build with the help of Antigravity

## 🔗 Deployed using Vercel

**[https://auraix-gd-go-c-build-with-ai.vercel.app/dashboard](https://auraix-gd-go-c-build-with-ai.vercel.app/dashboard)**

---

## The Problem

Early-stage co-founders operate across 6–11 disconnected tools simultaneously. Decisions made on Tuesday evaporate by Friday. Paul tells an investor a feature is live — Sam deprioritised it three days ago. These small misalignments compound silently into broken commitments and damaged trust. No existing tool catches these conflicts before they cause damage.

---

## What SyncGuard Does

SyncGuard is an AI-powered decision log that actively monitors for contradictions. Both founders log decisions — typed, pasted from Slack, or via voice note. The AI extracts structured summaries, stores them in a vector database, and flags conflicts in real time with a severity level, plain-English explanation, and suggested resolution.

A colour-coded Daily Briefing surfaces each founder's top priorities every morning, drawing from open conflicts, pending decisions, and synced Google Calendar events.

---

## How the AI Works

- **Extract** — Gemini 1.5 Flash parses raw input into a structured decision summary with entities, category, and intent
- **Embed** — text-embedding-004 converts the summary into a vector stored in ChromaDB
- **Retrieve** — the top semantically similar prior decisions are fetched via vector search
- **Reason** — the LLM compares the new decision against candidates and classifies any conflict: `contradiction`, `stale_information`, `broken_commitment`, or `overlap`
- **Rank** — the Daily Briefing agent ranks all open items by urgency into `critical` / `high` / `normal` / `info` priority tiers

Rule-based matching cannot do this — semantic understanding of intent across different phrasings and contexts requires AI.

---

## Features

- Decision logger — text, Slack paste, or voice note input
- Real-time conflict detection with severity badge and resolution suggestion
- Conflict inbox — sortable by severity, one-click resolve
- Colour-coded daily briefing per founder
- Full decision log — filterable by founder, category, date, status
- Auth — email/password signup and Google OAuth

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Next.js 14 (App Router), Tailwind CSS, Shadcn/ui |
| Backend | FastAPI (Python) |
| AI / LLM | Google Gemini 1.5 Flash |
| Embeddings | Google text-embedding-004 |
| Vector DB | ChromaDB (open-source) |
| Database | Supabase (PostgreSQL) |
| Auth | Supabase Auth (email + Google OAuth) |
| Voice | OpenAI Whisper (open-source, local) |
| Calendar | Google Calendar API (read-only OAuth) |
| Deployment | Vercel (frontend), Cloud Run / Railway (backend) |

---

## Third-Party Disclosures

| Tool / API / Library | Purpose | License / Cost |
|---------------------|---------|---------------|
| Google Gemini 1.5 Flash | Core LLM for all AI reasoning | Free tier (AI Studio) |
| Google text-embedding-004 | Semantic embeddings | Free tier |
| ChromaDB | Vector similarity search | Apache 2.0 / Free |
| OpenAI Whisper | Voice transcription (local) | MIT / Free |
| Supabase | Database + Auth | Free tier |
| Google Calendar API | Read-only calendar events | Free |
| Google OAuth 2.0 | Authentication | Free |
| Next.js 14 | Frontend framework | MIT / Free |
| Tailwind CSS | Styling | MIT / Free |
| Shadcn/ui | UI components | MIT / Free |
| FastAPI | Backend API framework | MIT / Free |
| Vercel | Frontend deployment | Free tier |
| AntiGravity | Backend code | Free tier |
---

## Team

- Muskan Irfan
- Noor Ul Sabah
- Afaf Yunus

---
