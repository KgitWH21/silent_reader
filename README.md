# Silent Reader – Beta Reader App

> **Turn vague beta‑reader notes into actionable insights.**
>
> Silent Reader lets authors share a private link to their manuscript so readers can highlight text, tag issues, and leave contextual comments. The app then aggregates that feedback into an intuitive heat‑map so you can spot problem areas at a glance.

---

## Table of Contents

1. [Features](#features)
2. [Tech Stack](#tech-stack)
3. [Getting Started](#getting-started)
4. [Project Structure](#project-structure)
5. [Roadmap](#roadmap)
6. [Contributing](#contributing)
7. [License](#license)

---

## Features

* **Inline Highlights & Tags** – Readers mark sentences or paragraphs and label issues (e.g. *typo*, *slow pacing*, *awesome*).
* **Real‑Time Sync** – Feedback shows up instantly via Firebase.
* **Heat‑Map Dashboard** – Visual overlay pinpoints hotspots in the text.
* **Shareable Draft Links** – One URL per manuscript; no account required for readers.
* **Author Privacy** – Only people with the link can view your draft.
* **Works Anywhere** – 100 % browser‑based; no installs or extensions.

## Tech Stack

| Layer           | Choice & Why                                                                            |
| --------------- | --------------------------------------------------------------------------------------- |
| Front‑end       | **HTML5 + CSS3 + Vanilla JS (ES6)** – zero framework overhead; easy to learn and extend |
| Back‑end / Sync | **Firebase** – Auth, Firestore, and Hosting handle realtime data and deployment         |
| Tooling         | **Firebase CLI (optional)** – single‑command deploy & local emulators                   |

> **No React, Vue, or bundlers**—just lean, standards‑based web tech.

## Getting Started

### Prerequisites

* A free **Firebase** project
* (Optional) **Node.js ≥ 18** to run the Firebase CLI for local emulation and deploy (`npm i -g firebase-tools`).

### 1. Clone

```bash
git clone https://github.com/<your‑user>/silent-reader.git
cd silent-reader
```

### 2. Configure Firebase

1. In the Firebase console create a project and add a Web App.
2. Copy the config snippet and paste it into `/js/firebaseConfig.js`:

```js
// js/firebaseConfig.js
export const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  projectId: "...",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

### 3. Run Locally

Because there’s **no build step** you can open `index.html` directly or serve the folder:

```bash
# VS Code Live Server, Python http.server, or:
npx http-server .
```

### 4. Deploy

```bash
firebase login            # first time only
firebase init hosting      # choose “public” directory (./)
firebase deploy            # done!
```

## Project Structure

```
silent-reader/
├── index.html
├── css/
│   └── styles.css
├── js/
│   ├── app.js            # core logic
│   ├── firebaseConfig.js # your keys (never commit real keys)
│   └── utils/
│       └── heatmap.js
└── assets/               # images / icons
```

## Roadmap

* [ ] Drag‑and‑drop manuscript import (.md / .docx)
* [ ] Advanced filters (by tag, reader)
* [ ] Export feedback (CSV / JSON)
* [ ] Sentiment analysis on comments
* [ ] Offline mode (IndexedDB cache)

## Contributing

Pull requests are welcome! Open an issue first to discuss changes or new features.

1. Fork → `git checkout -b feature/my-feature`
2. Commit → `git commit -m "Add My Feature"`
3. Push → `git push origin feature/my-feature`
4. Open a PR.

## License

MIT

---

*Built with ❤️ by Keith Hayden & contributors.*
