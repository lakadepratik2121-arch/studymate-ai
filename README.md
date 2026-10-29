# StudyMate AI
**Your notes. Your AI. Your success.**

An AI-powered study workspace that turns notes or a topic into a **summary, a 5-question quiz and flashcards**.
Built with plain HTML, CSS and JavaScript for Web Technology CA Assignment 5.

## Features
- Real AI generation via the Google Gemini API (`fetch`, `async/await`, `POST`, JSON body)
- Summary with Copy, Download `.txt`, Read Aloud / Stop (SpeechSynthesis) and Regenerate
- Interactive quiz: one question at a time, progress bar, feedback + explanations, score, answer review, restart
- Flashcards: click to flip, previous/next, known / not-known tracking, keyboard arrows
- Study history in localStorage: reopen, continue, search, delete, clear all
- Dark / light mode (remembered), explanation styles, difficulty levels, character counter, progress summary
- Full error handling: empty input, too-long input, missing key, 401/403, 429, other HTTP errors, network failure, invalid AI JSON
- Responsive layout (phone, tablet, laptop)

## Technologies
HTML5, CSS3 (Grid + Flexbox + media queries), vanilla JavaScript (ES6+). No frameworks or build tools.

## Folder structure
```
studymate-ai/
├── index.html
├── style.css
├── script.js
├── README.md
└── assets/logo.svg
```

## Run locally
1. Download or clone the folder.
2. Double-click `index.html`, or run `npx serve .` / VS Code "Live Server".
3. Open **Settings**, paste your API key, click **Save**.

## Get a free API key
1. Go to <https://aistudio.google.com/apikey> and sign in with a Google account.
2. Click **Create API key** and copy it.
3. Paste it in StudyMate AI → Settings → Save.

Docs: <https://ai.google.dev/gemini-api/docs> · Models list: <https://ai.google.dev/gemini-api/docs/models>
The model name is editable in Settings (default `gemini-3-flash-preview`). If you get "model not found", pick a current one from the list.

## How to test
- Click **Try an example** → **Generate Study Material**.
- Check the 3 tabs; finish the quiz and see the review; flip flashcards; copy/download/read aloud.
- Refresh the page: theme and history remain.
- Error tests: empty notes, no key, wrong key (401/403/400), turn Wi-Fi off, notes > 12000 characters.

## Deploy
**GitHub:** `git init` → `git add .` → `git commit -m "StudyMate AI"` → create a repo on github.com → `git remote add origin <url>` → `git push -u origin main`.
**Netlify:** drag the folder onto <https://app.netlify.com/drop>. **Vercel:** import the GitHub repo, framework preset "Other", no build command, output directory `.`.

## Security notes (honest limitations)
- The API key is typed by the user and stored in **localStorage**, which is **not secure**: scripts on the page or anyone using the device can read it, and the browser's Network tab shows it.
- Never commit a real key. This repo contains none.
- A public production app should call the AI through a **backend proxy** that keeps the key secret. This project uses the user-provided-key approach required by the assignment.
- AI output can be wrong; always check important facts. Free tiers have rate limits.

## Screenshots
_Add screenshots here (dashboard, study room, quiz, mobile view). Never show your API key in them._
