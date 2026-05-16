[README.md](https://github.com/user-attachments/files/27860984/README.md)
# Daily Planner — Deployment Guide

## Step 1: Set up Supabase database

1. Go to your Supabase project → **SQL Editor**
2. Copy the entire contents of `setup.sql`
3. Paste and click **Run**
4. You should see "Success" for each statement

## Step 2: Push to GitHub

1. Go to github.com → New repository → name it `daily-planner` → Create
2. On the new repo page, click **uploading an existing file**
3. Upload `index.html` (that's the only file Vercel needs)
4. Commit

## Step 3: Deploy to Vercel

1. Go to vercel.com → **Add New Project**
2. Select your `daily-planner` GitHub repo
3. Click **Deploy** (no configuration needed — it's a static HTML file)
4. Wait ~30 seconds → your app is live at a `.vercel.app` URL

## Step 4: Use on any device

Open the Vercel URL on any device. Sign up once, then sign in anywhere.

## Updating the app

When you get an updated `index.html`:
1. Go to your GitHub repo
2. Click `index.html` → Edit (pencil icon) → paste new content → Commit
3. Vercel automatically redeploys in ~30 seconds

---

## What's stored where

| Data | Storage |
|------|---------|
| Tasks | `tasks` table (one row per task) |
| Notes | `day_notes` table (JSONB per day) |
| Whiteboards | `whiteboards` table (JSONB per day) |
| Files & Images | Supabase Storage + `attachments` table |

## Free tier limits (more than enough for personal use)

- Supabase: 500MB database, 1GB file storage, 50,000 monthly active users
- Vercel: Unlimited deploys, 100GB bandwidth/month
