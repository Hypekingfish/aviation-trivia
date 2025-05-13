# ✈️ Aviation Twitch Trivia Script for Streamer.bot

Bring aviation-themed trivia to your Twitch stream with this interactive, chat-driven C# script built for [Streamer.bot](https://streamer.bot)! Perfect for VATSIM streamers, flight simmers, and aviation enthusiasts, this script adds a fun and educational way to engage your viewers.

---

## Install
- Drag and drop purchased file into the streamerbot import window

---

## 🎯 Features

- ✅ Over **30+ trivia questions** across aviation-related categories
- ✅ **Random or category-based** question selection (e.g., `!trivia aircraft`)
- ✅ Accepts **multiple correct answers** (aliases and variations)
- ✅ Built-in **hint system**
- ✅ Uses **Streamer.bot global variables** for real-time state tracking
- ✅ Random emoji flair for variety
- ✅ Logging for debugging and stats
- ✅ Scoring system with a **leaderboard**
- ✅ Moderator-only scoreboard **reset command**

---

## 💬 How it works

When a user runs the trivia command (e.g., `!trivia` or `!trivia airports`):

1. The script checks if a question is already active.
2. It picks a random trivia question (optionally filtered by category).
3. Stores all required data in global variables:
   - `triviaAnswerList`
   - `triviaCorrectAnswer`
   - `lastTriviaQuestion`
   - `lastTriviaHint`
   - `triviaActive`
4. Posts the question to chat and logs info to the Streamer.bot log console.
5. Awaits an answer from chat.
6. Viewers type their answers. The answer checker script compares answers to the correct ones, tracking wrong guesses.
7. First correct answer wins points, disables the question, and optionally gives a hint if needed.

---

## 🧠 Trivia Categories

- ATC
- Airspace
- Aircraft
- Airports
- Navigation
- Forecast
- Airlines

You can run trivia in a specific category using:

```
!trivia [category]

```

---

## 🧩 Additional Scripts

### ✅ Answer Checker

This script checks chat messages during an active trivia question. It compares the user's message against the stored answer list. If correct:

- Announces the winner
- Increments the user's score
- Updates a scoreboard of participants
- Resets `wrongGuesses`

If incorrect:

- Tracks incorrect guesses
- Gives a hint every 3 wrong answers

### 🏆 Leaderboard Display

Displays the top 5 trivia scorers and shows honorable mentions if the sender isn't in the top 5.

Command: `!triviascores` (or your preferred command)

Variables used:

- `triviaScoreboardUsers` (CSV of usernames)
- `triviaScore_<user>` (individual scores)

### 🧹 Scoreboard Reset

This **mod/broadcaster-only** script resets all scores.

- Clears all saved scores in `triviaScore_<user>`
- Empties the scoreboard user list
- Outputs confirmation message

Only accessible to Twitch moderators or the broadcaster.

---

## ✅ Example Output

```
🧠 [Trivia: Aircraft | Hard] First to answer wins: What does 'TCAS' stand for?
```

**Correct answer:** `traffic collision avoidance system`

When answered correctly:

**hypekingfish** got it right first! The correct answer was: traffic collision avoidance system

Leaderboard sample output:

`Only one participant: hypekingfish — 6 points!  1st: hypekingfish — 6 points Total participants: 1`

---
