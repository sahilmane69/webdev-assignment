# StudyForge - AI Study Assistant

StudyForge is a small web app for students. You paste your class notes (or type a topic) and the app uses the
Google Gemini API to create:

1. a short summary,
2. a quiz with exactly five multiple-choice questions, and
3. flashcards you can flip and track.

It is built for **Web Technology Assignment 5** with only HTML5, basic CSS3 and vanilla JavaScript
(no frameworks, no build step, no backend). The design is a simple, Codeforces-inspired academic layout.

## Screenshot

![StudyForge screenshot](screenshots/img.png)`

## Features

- Notes/topic input with a live character counter, a warning near the limit (12,000 characters) and generation disabled when over the limit
- Difficulty selector (Easy / Medium / Hard) and answer style (Explain Like I'm 10 / Exam-Focused / Detailed)
- **Summary tab:** Copy, Download as TXT, Read Aloud and Stop Speaking (browser Speech Synthesis API)
- **Quiz tab:** exactly 5 questions, one answer each, score, correct answers and explanations, no double submit, Retake button
- **Quiz scores:** best score and recent scores saved in localStorage
- **Flashcards tab:** click or press Enter to flip (CSS flip effect), Known / Not Known tracking with a progress count, works on mobile
- **History:** saved in localStorage; search, reopen, regenerate, delete one item, Clear All with confirmation
- **Settings:** save / show-hide / clear your own API key (only the last 4 characters are ever displayed) and choose the model name
- Dark / Light mode saved in localStorage
- Handles empty input, missing key, 400/401/403/404/429/5xx errors, network failures, timeouts (60 s), blocked or empty AI replies, malformed JSON, invalid structure and corrupted localStorage

## Technologies used

- HTML5 (semantic elements, labels, ARIA roles for tabs and messages)
- CSS3 (CSS variables for themes, Flexbox, Grid, media queries)
- Vanilla JavaScript: DOM manipulation, events, arrays, objects, `async/await`, Promises, `fetch`, `AbortController`, JSON, `localStorage`, Clipboard API, Blob download, SpeechSynthesis API
- Google Gemini API (`generateContent` REST endpoint)



## How to get a free Gemini API key

1. Go to <https://aistudio.google.com/apikey> and sign in with a Google account.
2. Click **Create API key** (pick or create a project when asked).
3. Copy the key. Treat it like a password.

Free-tier limits and available models can change. Check the official pages if something does not work:
<https://ai.google.dev/gemini-api/docs/rate-limits> and <https://ai.google.dev/gemini-api/docs/models>.

## How to save and use the key in the app

1. Open **Settings** in the top menu.
2. Paste your key and click **Save API Key**. The page then shows only `****` and the last 4 characters.
3. Go back to **Study**, paste notes and click **Generate Study Material**.

Use **Show** to check what you typed before saving, and **Clear API Key** to remove it.
The default model is `gemini-3.5-flash-lite`. If your key gets a "model not found" or quota error, type another
model name from the official model list (for example `gemini-3.8-flash`) in Settings and click **Save Model**.


