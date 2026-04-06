# Yardbird's Song Trivia 🎵
Version 7.0
A real-time, Kahoot-style multiplayer song guessing game built for the web. Guess the artist, song title, or movie soundtrack as fast as you can. Play solo to climb the lifetime leaderboard, or host a Party Mode session and let your friends join via a dynamic QR code using their phones as controllers.

Developed by Karthik Raja.

---

## 🌟 Features

### 🎮 Game Modes
* **Classic Genre:** Guess the Artist and the Song from specific decades or custom genres. 
* **Artist-Specific:** Pure catalog recall. Focus entirely on a single artist.
* **Movie Mode:** Identify the cinematic film from its original soundtrack (e.g., Disney Classics, Bollywood Hits, Hollywood Blockbusters).
* **The "Today Three" Daily Challenge:** A globally synced 3-round challenge that resets every day.

### 👥 Party Mode (Kahoot-Style Multiplayer)
* **The Host Screen (TV/Laptop):** Creates a lobby, displays a dynamic QR code for instant phone pairing, visualizes the bouncing audio, and reveals the post-round scoreboards.
* **The Phone Controller:** Seamlessly joins via QR code or 4-letter room code. Displays adaptive input fields depending on the game mode, synchronized countdown clocks, and a giant final score reveal.
* **Massive Scaling:** Firebase backend allows an unlimited number of players to connect simultaneously with looping UI colors.

### ⚙️ Mechanics & Difficulty
* **Easy & Medium:** 30 seconds to guess. If you get stuck, a "Multiple Choice" lifeline automatically drops in at the 10-second mark to save you (capping points at a lower tier).
* **Hard Mode:** A brutal 10-second audio sprint. Pure recall typing. No lifelines.
* **The Grace Period:** In Party Mode, players get a silent 30-second grace period after the music ends to finish typing their answers on mobile keyboards.

---

## 📐 The Scoring Engine

Scores are mathematically normalized to a **Perfect 1000** regardless of how many rounds are played, allowing lifetime accuracy and high scores to be tracked fairly across all settings. 

**Raw Point Breakdown (Per Song):**
* **Perfect Typing (30s remaining):** Up to 60 Pts
* **Multiple Choice Lifeline (10s remaining):** Max 10 Pts
* **Grace Period Typing (0s remaining):** Flat 5 Pts
* **Streak Bonus:** Every 3 consecutive correct answers awards a flat **+50 Pts**.

---

## 🛠️ Tech Stack

* **Frontend:** Vanilla HTML, CSS, and JavaScript. No build steps or heavy frameworks required.
* **Backend & Multiplayer Synchronization:** Firebase Realtime Database.
* **Music Data:** Apple iTunes Search API (Live Audio Previews & Metadata).
* **QR Generation:** `qrcode.js` (Local lightweight rendering).

---

## 🚀 Setup & Installation

Because the game is built with pure web technologies, it can be hosted on any static file server. 

### 1. Local Testing
1. Clone the repository to your local machine.
2. Open `index.html` directly in any modern web browser.
3. *Note: The QR code scanner will only auto-join when hosted on a live URL. To test multiplayer locally, open multiple tabs and manually enter the 4-letter room code.*

### 2. Deploying to GitHub Pages
1. Rename your main HTML file to `index.html`.
2. Push your code to a public GitHub repository.
3. Go to your repository **Settings** > **Pages**.
4. Set the Source branch to `main` and save.
5. Your game will be live at `https://[your-username].github.io/`! 

### 3. Firebase Configuration
The game currently uses a default Firebase configuration. If you plan to scale the game or keep it public long-term, it is highly recommended to:
1. Create your own project at [Firebase Console](https://console.firebase.google.com/).
2. Enable the **Realtime Database**.
3. Set your read/write security rules.
4. Replace the `firebaseConfig` object at the top of the `<script>` section in `index.html` with your new project keys.

---

## 🏆 Lifetime Locker Room

The game utilizes `localStorage` to securely save your lifetime stats directly to your device. 
* **Trophy Cabinet:** Unlock achievements like *The Sniper* (10 hits under 3 seconds) and *The Daily Devotee* (5-day streak).
* **Performance Tracking:** Monitors global high scores, lifetime accuracy, and total matches played.
