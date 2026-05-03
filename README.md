# Bitewise

*cook with intention · eat with awareness*

A minimal, mobile-first web app that turns natural-language descriptions into structured recipes and uses AI vision to track your daily calorie intake from meal photos.

## Features

**Recipe Book**
- Describe a dish in any language → AI generates ingredients, steps, category, and cook time
- Attach photos for cover images and to give the AI visual context
- Library with category, cook time, and cross-language ingredient search
- Edit any saved recipe — change name, ingredients, steps, photo

**Food Log**
- Upload a meal photo → AI estimates calories, protein, carbs, fat
- Daily total with progress toward your calorie goal
- 7-day trend chart and full history sheet — browse any past day
- Macro breakdown (protein, carbs, fat) per day

**Account & sync**
- Sign in with Google — recipes & meal log sync across all your devices
- Or use guest mode (data stays on one device)
- Photos stored in Cloudinary, data in Firestore

## Setup

This is a single-file static web app — no build step. Just open `index.html` in a browser, or host it anywhere that serves static files (GitHub Pages, Firebase Hosting, Netlify, etc.).

### Required for full functionality

1. **Gemini API key** (free) — entered by each user on first use. Get one at [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
2. **Firebase project** — config is included in `index.html` (safe to commit per Firebase guidelines). Required services: Authentication (Google provider), Firestore Database
3. **Cloudinary account** (free) — required for photo sync across devices. Cloud name and unsigned upload preset configured in `index.html`

## Tech Stack

- Vanilla HTML / CSS / JavaScript (no framework, no build step)
- Firebase Auth + Firestore — user accounts and data sync
- Cloudinary — image storage
- Google Gemini API — recipe generation and meal photo analysis

## Privacy

- Recipe and meal data is stored under your private user account in Firestore
- Photos go to Cloudinary in a per-user folder
- Your Gemini API key never leaves your browser
- Firestore Security Rules ensure no other user can access your data
