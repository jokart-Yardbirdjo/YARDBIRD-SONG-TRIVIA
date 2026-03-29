# 🎵 Yardbird's Song Trivia

**The Ultimate High-Speed Music & Movie Soundtrack Challenge.**

Yardbird's Song Trivia is a fast-paced, mobile-first web game that pulls real-time audio from the vast iTunes API catalog. Designed for 1 to 4 players (pass-and-play), it tests your knowledge across decades of music, specific legendary artists, and international cinema soundtracks. 

Play it live here: [Insert Your GitHub Pages Link Here]

---

## 🚀 Key Features
* **Zero Server Required:** 100% front-end vanilla HTML, CSS, and JS. Runs entirely in the browser.
* **Real-Time Audio:** Leverages the Apple/iTunes Search API to fetch 30-second high-quality audio previews dynamically.
* **Mobile-First UI:** A sleek, single-column design with pinned horizontal "Score Pills" to keep the leaderboard visible on any device.
* **Anti-Repeat Engine:** A custom sanitizer tracks incoming API data to ensure no duplicate tracks (or "Remastered" variants of the same song) appear in a single game.
* **Playlist Exporter:** At the end of the game, automatically generates a clickable playlist of your session, with deep links natively routing to Apple Music, Spotify, or YouTube.
* **Local Hall of Fame:** Uses browser `localStorage` to persistently track and display the All-Time High Score on that specific device.

---

## 🎮 Game Modes

### 1. The Classic Era/Genre Sprint
Guess **both** the Artist and the Song Title based on the audio clip. Categories range from pre-1980s classics to modern hits, including a curated "Shwe Special" featuring legendary 90s Pop/Rock icons.

### 2. Artist Deep Dive
You already know the artist—now you just have to name the song. Choose from defaults like Taylor Swift or Michael Jackson, or enter a Custom Artist search. 

### 3. Cinema Scores (Movie Mode)
Listen to an audio clip and guess the **Movie or Soundtrack** it belongs to. 
* *Strict Validator Logic:* To prevent random pop songs from sneaking into movie rounds, the game actively filters API metadata, rejecting any track whose `primaryGenreName` or `collectionName` does not explicitly contain tags like "Soundtrack", "OST", "Motion Picture", "Bollywood", or "Tamil".

---

## ⏱ Answer Formats & Pacing

* **Type Answers (Classic):** Players listen to the track and must click "STOP & GUESS". This pauses the audio and triggers a **20-Second Hot Seat Timer**. If the player fails to type their answer before the timer hits zero, they are buzzed out.
* **Multiple Choice (Fast Paced):** Three options are instantly generated on-screen (1 correct, 2 dynamically pulled from the active category pool). The player must tap the correct answer while the music is playing before the main round timer expires. 

---

## 🧮 Scoring System

The game heavily rewards speed and accuracy. 

* **Speed Points:** `30 - Seconds Elapsed`. The faster you buzz in or click the correct multiple choice button, the higher your base score. 
* **The Perfect Double:** (Classic Typing / Mode 1 Only). If a player successfully identifies BOTH the Artist and the Song correctly, their base points for that round are multiplied by **2x**.
* **Streak Bonus:** An instant **+50 Point Bonus** is awarded for every 3 consecutive correct rounds. Failing a round resets your streak to 0.

---

## 🧠 Under the Hood: Advanced Fuzzy Matching

To make the game fair—especially when typing out long song titles or transliterated international movie names—the game utilizes a highly forgiving custom evaluation engine:

1. **Sanitization:** Strips out bracketed text like `(Original Motion Picture Soundtrack)` from the API response so players don't have to type it.
2. **Phonetic Reduction:** To handle complex Bollywood/Tamil movie names, the engine collapses double vowels (`aa` becomes `a`), maps `y` to `i`, and strips out `h` (making `th` equal `t`). This allows a user typing `vinai thandi` to perfectly match `Vinnaithaandi`.
3. **Levenshtein Distance:** Calculates the mathematical edit distance between the guess and the actual answer, allowing for minor typos (e.g., matching at a 70% similarity threshold).
4. **Keyword Overlap:** Checks for word-by-word matches, ignoring generic words under 3 letters unless absolutely necessary. A 60% keyword match results in a "Close Enough!" correct answer.

---

## 🛠 Tech Stack
* **HTML5:** Semantic structure.
* **CSS3:** Custom properties (variables), Flexbox layout, responsive media queries.
* **JavaScript (ES6+):** Async/Await fetching, DOM manipulation, custom algorithms. 
* **API:** iTunes Search API (`https://itunes.apple.com/search`)

---

## 📥 Deployment
Because the entire application is contained within a single `index.html` file, deployment takes seconds. 
1. Fork or clone this repository.
2. Enable **GitHub Pages** in your repository settings (pointing to the `main` branch).
3. Play! No build steps, Node modules, or servers required.

---
*Created for the love of music trivia.*
