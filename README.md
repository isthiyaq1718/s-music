# Waveform (s-music)

A single-file, front-end music streaming UI prototype — playlists, search, a full player, and free song playback via YouTube/SoundCloud embeds or direct audio files. No backend required to run it.

**Live demo:** https://isthiyaq1718.github.io/s-music/

## Features

- **Home / Search / Library / Favorites / Now Playing** screens, with a desktop sidebar and mobile bottom nav
- **Playlists** — 9 built-in playlists, podcasts, and a live-stream demo
- **Search** — filters playlists and individual songs live as you type
- **Playback**
  - Real seekable audio player (tap or drag the progress bar to jump forward/backward)
  - YouTube embed playback for songs with a video link
  - SoundCloud embed playback (visual player) for songs with a track link
  - Direct audio file playback (mp3/wav/etc., including Firebase Storage links)
- **Add Song** — paste a YouTube link, SoundCloud link, or direct audio URL to add a new song on the fly
- **Firebase Storage integration** — optionally auto-loads every song uploaded to a `songs/` folder in your Firebase Storage bucket
- **Favorites** — heart any playlist to save it

## Getting started

This is a single static HTML file — no build step, no dependencies to install.

### Run locally
Open `index.html` directly, or serve it so embeds/audio work properly:
```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

### Deploy
Already live via **GitHub Pages** at the link above. To redeploy after changes:
1. Push/upload your updated `index.html` to this repo
2. Go to Settings → Pages → confirm branch is `main`, folder `/ (root)`
3. Changes go live within a couple of minutes

## Optional: connect Firebase Storage

To auto-load your own uploaded songs:

1. Create a free project at [firebase.google.com](https://firebase.google.com), enable **Storage**
2. In `index.html`, find the `firebaseConfig` object and replace the placeholder values with your project's config (Project settings → General → Your apps)
3. Upload audio files under a `songs/` folder in the Storage console
4. Set Storage rules to allow public read if you want songs to load without login:
   ```
   allow read: if true;
   allow write: if false;
   ```
5. Optional: set custom metadata `title` and `artist` on each file — otherwise the filename is used as the title

## Notes

- Some songs use third-party SoundCloud/YouTube reuploads for demo purposes — these depend on the original uploader keeping the content live and embeddable, and are not official releases.
- Playlist track audio uses royalty-free demo clips as stand-ins (no licensed music is bundled).

## License

Add your preferred license here (e.g. MIT).
