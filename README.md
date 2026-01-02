# Cyber-Sonix · Engine

**Cyber-Sonix Engine** is an offline-first cyber music engine built for the web.  
It enables local audio streaming, persistent favorites, and smooth playback using modern browser APIs and IndexedDB — all wrapped in a futuristic, minimal UI.

> Designed for performance, persistence, and a modern listening experience.

---

## ✨ Features

- 🎧 Local audio playback (files & folders)
- 💾 Offline-first architecture using IndexedDB
- ❤️ Persistent favorites (stored across sessions)
- ⚡ Fast, client-side data access (no backend required)
- 🧠 Clean separation of data, state, and UI logic
- 🎨 Cyber / neon inspired UI design
- 🌐 Fully browser-based (no uploads, no cloud dependency)

---

## 🧱 Architecture Overview

UI (HTML / CSS / JS)
↓
In-memory State (library, favorites)
↓
IndexedDB (source of truth)
├── songs
└── fav_songs

yaml
Copy code

- IndexedDB acts as the persistent data layer
- In-memory arrays act as derived UI state
- UI renders only from memory, never directly from the database

---

## 🗄️ IndexedDB Structure

### songs store
```js
{
  id: number,
  name: string,
  artist: string,
  size: number,
  data: Blob
}
fav_songs store
js
Copy code
{
  songId: number,
  addedAt: number
}
songId is used as the primary key to avoid duplicates and ensure fast lookup.

🚀 Getting Started
Clone the repository
bash
Copy code
git clone https://github.com/your-username/cyber-sonix-engine.git
cd cyber-sonix-engine
Run the app
Open index.html in a modern browser (Chrome / Edge recommended).

🎮 How It Works
User selects local audio files or folders

Files are stored as Blobs in IndexedDB

Songs are loaded into memory for fast access

Favorite toggles update IndexedDB directly

UI re-renders from updated state

🧠 Design Philosophy
Offline by default

No backend dependency

Data-driven UI

Single source of truth

Scalable and maintainable architecture

This project follows real-world application patterns used in PWAs and offline-first apps.

🛠️ Tech Stack
JavaScript (Vanilla)

IndexedDB

HTML5 Audio API

CSS (Cyber / Neon UI)

Browser File API

📌 Future Enhancements
Shuffle & repeat persistence

Progressive Web App (PWA) support

Advanced search & filtering

Audio equalizer & effects

Optional cloud sync

👨‍💻 Author
Vinay
Engineering student & developer
Focused on modern web architecture, offline-first systems, and clean UI design.
