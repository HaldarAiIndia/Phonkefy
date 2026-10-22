# Phonkefy — Phonk Music Player

A minimal, retro-styled web music player that streams YouTube playlists in the browser. No sign-up, no download, no backend.

🌐 **Live site:** https://phonkefy.vercel.app

---

## Features

- 🎵 Non-stop playback of any public YouTube playlist (phonk, drift phonk, trap, hip hop and more)
- 🔀 Previous / next with wrap-around, play / pause and click-or-touch seeking
- 💿 Floating player pill with a spinning album-art disc
- 📚 Playlist library: add your own YouTube playlist by URL or ID, with live verification
- 🔍 Search playlists and tracks inside the bottom-sheet menu
- 💾 Saves your playlists and your last selected playlist in the browser (`localStorage`)
- 🔒 Lock-screen and headphone controls through the Media Session API
- ⌨️ Press **Space** to play or pause
- 📱 Responsive layout for mobile and desktop
- 🔎 SEO-ready: meta tags, Open Graph, Twitter Card and JSON-LD structured data

---

## Project Structure

```
.
├── index.html     # The whole app (HTML + CSS + JavaScript)
├── bg.jpg         # Background image
├── favicon.png    # Favicon and social preview image
└── README.md
```

---

## Getting Started

### Run locally

The YouTube player needs `http://` or `https://` (not `file://`), so use a local server:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then open `http://localhost:8000`.

### Deploy to Vercel

1. Put `index.html`, `bg.jpg` and `favicon.png` in one folder (or repository).
2. Import it into [Vercel](https://vercel.com) or run `vercel` from that folder.
3. Keep `bg.jpg` and `favicon.png` next to `index.html` so they load.

---

## Customization

All settings are at the top of the `<script>` section in `index.html`:

| Setting | What it does |
| --- | --- |
| `DEFAULT_PLAYLIST_INPUT` | The playlist that loads by default (URL or ID) |
| `BACKGROUND_IMAGE_URL` | Background image (default `bg.jpg`) |
| `DEFAULT_ARTIST` | Fallback artist / author label |

To change the title, description or keywords, edit the meta tags at the top of `index.html`.

---

## How It Works

- **Playback:** YouTube IFrame Player API in a hidden player; the visible interface is custom.
- **Track info:** read from the player, with extra titles fetched from [noembed.com](https://noembed.com) and cached locally.
- **Storage:** playlists, active playlist and track metadata are stored in `localStorage` only. Nothing is sent to a server.

---

## Notes and Limitations

- Playlists must be **public** and allow embedding. Private playlists, and some auto-generated mixes (IDs starting with `RD`), may not load.
- Tracks that YouTube restricts are skipped automatically.
- Some mobile browsers block autoplay until you tap play.
- Music is streamed from YouTube. All content belongs to its respective owners.

---

## Tech Stack

HTML5 · CSS3 · Vanilla JavaScript · YouTube IFrame API · Media Session API

---

## Author

**Subhojit Haldar**
Founder, **HaldarAi** (unregistered company)

---

## License

© 2026 Subhojit Haldar, HaldarAi. All rights reserved.
