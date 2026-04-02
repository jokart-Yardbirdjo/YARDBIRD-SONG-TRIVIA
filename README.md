# 🎸 Yardbird's Song Trivia: Master Edition (v3.7)

**Yardbird's Song Trivia** is a highly polished, serverless, front-end web application that turns any screen into a competitive music trivia game night. Powered dynamically by the iTunes API, it features advanced fuzzy-string matching, robust metadata scrubbers, and a true standalone PWA (Progressive Web App) mobile experience.

Play the live version here: https://jokart-yardbirdjo.github.io/YARDBIRD-SONG-TRIVIA/

---

## 🌟 Key Features

### 🎮 Three Distinct Game Modes
* **Mode 1: Decades & Genres:** Test your knowledge on classic rock, 90s pop, or the heavily curated "One-Hit Wonders" mode. 
* **Mode 2: Artist specific & Mixtapes:** Guess the song from a specific artist. Type multiple artists separated by commas (e.g., `Queen, Adele, Prince`) to instantly generate a custom multi-artist mixtape challenge.
* **Mode 3: Cinema & Soundtracks:** Guess the movie based on the soundtrack. Supports Disney, Hollywood, Bollywood, Tamil, and custom searches (e.g., `Hindi, 90s` or `A.R. Rahman`).

### ⚙️ Advanced Engine Logic & API "Bouncers"
Apple's iTunes API is notoriously messy. Yardbird's engine includes industrial-strength scrubbers to ensure perfect gameplay:
* **The Compilation Killer:** A deep Regex blocklist actively scans albums and song titles, incinerating "Greatest Hits," "Lofi Covers," and "Karaoke" tracks to ensure only original anthems and movie soundtracks are played.
* **The "Grease" Protocol:** In Movie Mode, the engine scans hidden metadata to guarantee random English pop songs don't bleed into regional (Bollywood/Tamil) movie categories.
* **Deep Pool True Shuffle:** Bypasses API limitations to pull up to 300 tracks and truly randomize them, ensuring deep-cuts and zero repetition between games.
* **Anti-Spoiler Hint Scrubbers:** Actively deletes giveaway phrases like `(From "The Matrix")` or `& ZOMBIES - Cast` before they render on the hint screen.

### 🧠 Forgiving "Fuzzy Logic" 
No need to be a perfect typist under pressure. The game uses a custom Levenshtein distance algorithm:
* Ignores special characters and punctuation.
* Allows sliding-scale typo leniency for longer words (e.g., "Pocohantas" triggers a match for "Pocahontas").
* Matches compound words and partial strings.

### 🏆 Competitive Multiplayer & Scoring
* **Up to 4 Players:** Pass-and-play mechanics with color-coded UI indicators.
* **The 750-Point Normalizer:** Whether you play a 3-round sprint or a 20-round marathon, the engine mathematically calculates your maximum possible raw score and perfectly normalizes it to a clean 750-point ceiling for true leaderboard tracking.
* **Difficulty Scaling:** Play on **Easy** (standard 30s snippet) or **Hard** (a merciless 10-second intro cutoff with a 3x point multiplier).

### 📱 Premium UX & PWA Support
* **True Native App Feel:** Save it to your iOS or Android home screen for a fullscreen, browser-bar-free experience with a custom app icon.
* **Fair-Play Audio Sync:** The game clock refuses to start ticking until the audio has successfully buffered and hit the user's ears.
* **Dynamic Audio Visualizers:** Neon equalizer bars bounce to the music and dynamically change color to match the active player.
* **Playlist Export:** At the end of the game, instantly export your session's tracklist to Apple Music, Spotify, or YouTube.

---

## 🚀 How to Run Locally

Because Yardbird is a 100% serverless front-end application, there are no dependencies, node modules, or build steps required.

1. Clone or download this repository.
2. Open `index.html` in any modern web browser.
3. Start playing!

---

## 🛠️ Tech Stack
* **HTML5:** Semantic structure and layout.
* **CSS3:** Custom styling, CSS variables for dynamic theming, and keyframe animations.
* **Vanilla JavaScript (ES6+):** Async/Await API fetching, Levenshtein algorithms, and DOM manipulation. No frameworks required.
* **API:** Apple iTunes Search API.

---

## 📜 Recent Updates (v3.1 - v3.7)
* **v3.7:** Added "One-Hit Wonders" mode, Multi-Constraint custom parsing (e.g., `1980s, Pop`), Hit Density overhaul, and the Epic Intros (Hard Mode) 10-second cutoff.
* **v3.6:** Implemented "Deep Pool Shuffle" to fix seed repetition, and added "The Grease Protocol" to lock down Bollywood/Tamil metadata.
* **v3.5:** Built the "Chunk Filter" to strip Cast/Ensemble names from hints, and upgraded the Compilation Killer regex.
* **v3.4:** Added the "From [Movie]" scrubber to prevent song titles from spoiling Movie Mode.
* **v3.2:** Introduced the Comma-Separated Mixtape fetch for Artist mode, Duplicate Track Killer, and single/EP rejector.
* **v3.1:** Added the 750-Point Score Normalizer, Fair-Play Audio Sync, dynamic color-coded visualizers, CSS UI fade-ins, and the endgame Confetti Cannon. 

---

## 📝 License
This project is for educational and entertainment purposes. Audio previews and metadata are provided by the iTunes Search API.
