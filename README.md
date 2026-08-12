Approximate (per 100g), not lab-measured — treat them as a general guide.
- No accounts or sync across devices — data lives wherever the artifact's storage is scoped to.

## Possible next steps

- Date picker / history view to browse past days instead of just today
- Weekly summary stats (avg calories, total sessions)
- Coach commentary extended to the meals tab# Field Log — Meals & Workout Tracker

A single-file HTML app for logging daily meals (via a bundled food calorie database, including Nigerian dishes) and workouts (with exercise suggestions, saved routines, and a lightweight coach that comments on your consistency).

## Features

**Meals**
- Instant local search over ~170 foods (with calories per 100g), including a set of common Nigerian dishes, snacks, and drinks
- Add your own foods on the fly — anything not in the list gets saved for future searches
- Adjustable quantity (grams) with live calorie recalculation
- Daily totals and a running list of everything logged that day

**Workouts**
- Log exercises with sets, reps, and weight
- Live exercise-name suggestions as you type (~65 built-in exercises across major muscle groups, plus anything you've logged before)
- Save routines (e.g. "Push day") as a group of exercises, then add the whole routine to today's log in one tap
- A "Coach" card that reads your actual logged dates to track streaks, flag long gaps since your last session, and nudge toward rest days if you've gone a full week straight
- A short random encouragement message after each logged exercise

## How data is stored

All data (meals, workouts, routines, custom foods) is saved with the Claude artifact `window.storage` API. This means:
- Your data **persists automatically** between sessions — no login, no setup
- Data is **personal to you** (not shared with anyone else)
- This only works while the app is running **inside a Claude.ai artifact view**. If you download the `.html` file and open it directly in a browser outside Claude, the storage calls (and anything else relying on the Claude environment) won't function.

## Running it

Open `training-log.html` inside Claude — either as a shared artifact link or by re-uploading it to a conversation and asking Claude to open/render it. There's no build step; it's plain HTML/CSS/JS with Google Fonts loaded from a CDN.

## Known limitations

- The food and exercise databases are hardcoded reference lists, not live nutrition APIs — the sandbox this runs in blocks outbound network calls to third-party services, so anything beyond the bundled data has to be added manually.
- Calorie values are a
