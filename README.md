# Smusiic

A Spotify-style music streaming web app UI, built from scratch as a personal frontend/UI-UX project. Home feed, search, playlists, a full now-playing screen, favorites, and a persistent mini-player — all in plain HTML, CSS, and JavaScript.

**Live demo:** https://smusiic.tiiny.site

> Personal/portfolio project. Not affiliated with or endorsed by Spotify or any streaming service — the dark theme + green accent UI is just a familiar, tested layout to design and build against.

## Features

- **Home** — quick-access playlist grid, "Made for you" and "Recently played" rows, filter chips (All / Music / Podcasts / Live)
- **Search** — live filtering as you type, plus an "Add Song" modal for pasting a YouTube link, SoundCloud link, or direct audio URL
- **Playlists & Now Playing** — full-screen player with seek bar, elapsed/duration time, next/prev, and a heart icon to favorite the current playlist
- **Library & Favorites** — dedicated screens backed by the same playlist data
- **Playback engine** handles three sources automatically:
  - Native `<audio>` element for direct file URLs
  - Embedded YouTube iframe player for YouTube links
  - Embedded SoundCloud widget for SoundCloud links
- **Google Sign-In** — real Google Identity Services integration; greeting and avatar update with the signed-in profile
- **Responsive layout** — sidebar + persistent mini-player on desktop, bottom tab bar + splash screen on mobile
- **Optional Firebase Storage hookup** — point it at your own bucket to pull in real uploaded audio files automatically (off by default)

## Tech stack

- Vanilla HTML, CSS, and JavaScript — no framework, no build step
- [Google Identity Services](https://developers.google.com/identity/gsi/web) for sign-in
- YouTube IFrame Player API + SoundCloud Widget API for embedded playback
- Firebase Storage (compat SDK) — optional, for loading self-hosted audio

## Demo audio note

Fictional song titles (e.g. "Amber Skyline", "Neon Static") play royalty-free sample clips from SoundHelix, deterministically mapped so the same title always plays the same clip — no licensed music files are bundled. A few real songs (Michael Jackson tracks, a couple of Tamil/Hindi film songs) stream via public YouTube/SoundCloud embeds rather than hosted files.

## Running locally

No installation or build step — it's static files.

```bash
git clone https://github.com/<your-username>/smusiic.git
cd smusiic
open index.html   # or just double-click the file
```

## Project structure

```
smusiic/
├── index.html   # markup for all screens (home, search, playlist, now playing, library, favorites)
├── style.css    # dark theme, layout, responsive rules
└── script.js    # app state, routing between screens, playback engine, auth
```

## Optional: connect your own audio

To load real uploaded songs instead of relying only on YouTube/SoundCloud links:

1. Create a free project at [firebase.google.com](https://firebase.google.com) and enable Storage
2. In `script.js`, replace the placeholder `firebaseConfig` values with your project's config (Project settings → General → Your apps)
3. Upload audio files under a `songs/` folder in the Storage console (optionally set `title`/`artist` custom metadata on each file)
4. Set Storage rules to allow public read if the page should load without login

## Author

Built by Isthiyaq as a personal project to practice frontend development, UI/UX design, and client-side JavaScript.

## License

MIT
