# VoiceNotes AI 🎙️

A sleek, single-file voice note-taking web app with real-time speech-to-text transcription, AI-powered summarization, and a glassmorphism UI. No backend required — everything runs in the browser.

---

## Features

- **Voice Recording** — Record audio using the browser's MediaRecorder API with a one-click Record button
- **Live Transcription** — Real-time speech-to-text via the Web Speech API displayed in a live transcript banner while recording
- **AI Summaries** — Automatically generates a concise title/summary for each note using the Claude API (claude-sonnet-4) after recording stops
- **Workspaces** — Organize notes into two workspaces: **General** and **Office**, switchable via a slider in the header
- **Time-based Filtering** — Filter notes by Today, This Week, This Month, This Year, or Older
- **Search** — Full-text search across note summaries and transcripts with highlighted matches
- **Sorting** — Sort notes by Newest, Oldest, Longest, or Shortest
- **Masonry & Compact Views** — Toggle between a Pinterest-style masonry grid and a compact single-column list
- **Audio Playback** — Play back the original recorded audio for any note via the speaker button
- **Edit & Delete** — Edit note titles or permanently delete notes via confirmation modals
- **Copy** — Copy a note's transcript to the clipboard in one click
- **Export** — Download notes as a JSON file, filterable by time range (All, Today, Week, Month, Year, Older)
- **Persistent Storage** — Notes are saved to `localStorage`; audio blobs are stored in IndexedDB
- **Responsive Design** — Fully optimized for mobile and desktop, with touch-friendly controls and safe-area inset support

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI | Vanilla HTML/CSS/JS (single file) |
| Font | Plus Jakarta Sans (Google Fonts) |
| Speech-to-Text | Web Speech API (`SpeechRecognition`) |
| Audio Recording | MediaRecorder API |
| Audio Storage | IndexedDB (`vnotes_audio`) |
| Note Storage | `localStorage` (`vnotes_glass_pinterest_v1`) |
| AI Summarization | Anthropic Claude API (`claude-sonnet-4`) |
| Styling | CSS custom properties, glassmorphism, backdrop-filter |

---

## Getting Started

Since VoiceNotes AI is a single self-contained HTML file, no build step or server is required.

1. **Open the file** — Open `index.html` directly in a modern browser (Chrome or Edge recommended for best Web Speech API support)
2. **Allow microphone access** — The browser will prompt for microphone permission on first use
3. **Start recording** — Click the **Record** button in the top-right header
4. **Stop recording** — Click the button again (it turns red while recording); an AI summary will be generated automatically
5. **Browse your notes** — Use filters, search, and sort controls to find notes

> **Note:** The Anthropic API key must be configured for AI summarization to work. Without it, notes are still saved with the raw transcript but without an AI-generated title.

---

## Browser Compatibility

| Browser | Recording | Transcription | Notes |
|---|---|---|---|
| Chrome / Edge | ✅ | ✅ | Recommended |
| Firefox | ✅ | ⚠️ | Web Speech API not fully supported |
| Safari (iOS 17+) | ✅ | ✅ | Works on modern iOS |

---

## Data & Privacy

- All notes and audio are stored **locally in your browser** — nothing is sent to any server except the transcript text sent to the Claude API for summarization.
- Clearing browser data (localStorage + IndexedDB) will permanently delete all notes and audio.
- Use the **Export** feature to back up your notes as a JSON file before clearing browser data.

---

## File Structure

```
index.html        # The entire app — HTML, CSS, and JavaScript in one file
README.md         # This file
```

---

## Keyboard & UI Controls

| Control | Action |
|---|---|
| Record button | Start / stop recording |
| Workspace slider | Switch between General / Office |
| Filter tabs | Filter notes by time period |
| Sort dropdown | Change note sort order |
| Masonry / Compact toggle | Switch layout view |
| Search bar | Search notes in real time |
| Card → Expand icon | Expand/collapse a note card |
| Card → Speaker icon | Play back original audio |
| Card → Copy icon | Copy transcript to clipboard |
| Card → Edit icon | Edit the note title |
| Card → Delete icon | Delete the note (with confirmation) |
| Export button | Download notes as JSON |
