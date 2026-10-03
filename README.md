# Holodeck

A single-file, AI-run text adventure. Answer 11 quick questions and a Game Master builds a story just for you, remembers everything, steers toward a real ending, and grades the result with a report card. Play by typing or hands-free by voice.

<!-- Add a screenshot here: ![Holodeck](screenshot.png) -->

## Features
- **Curated start:** 11 questions (genre, vibe, character, hook, length) shape your world.
- **Long-term memory:** story bible, lorebook, chapter summaries and hybrid keyword + semantic recall keep long stories consistent.
- **A plan behind the curtain:** secret roadmap, hidden GM secrets, and a "director" that varies pacing and flags repeated phrases.
- **Report card:** story grade, play grade, and a review of the secret roadmap at the end.
- **Hands-free voice:** dictation ("say *make it so* to send"), narrator voice, soft background sound, and automatic cleanup of misheard words.
- **You stay in control:** edit the bible and lore mid-story, undo a turn (memory included), watch the cost meter, save adventures as plain JSON files.

## Quick start
1. Get a free Gemini API key: https://aistudio.google.com/apikey
2. Open the app (see below) and paste the key on the welcome screen.
3. Press **Set up a new experience**.

No key yet? Choose **Try the offline demo** to look around with a fake Game Master.

### Running it
- **Hosted:** rename `holodeck-optimized.html` to `index.html`, push to a GitHub repo, and enable *Settings > Pages* (deploy from the main branch). Share the link; every player brings their own key.
- **Locally:** from the folder, run `python3 -m http.server 8080` and open `http://localhost:8080/holodeck-optimized.html`. (Opening the file directly works, but browsers then re-ask for microphone permission every time.)

### Browsers
| Browser | Typing | Dictation | Save to folder |
|---|---|---|---|
| Chrome / Edge | yes | yes | yes |
| Safari | yes | yes | no (use Export / Import) |
| Firefox | yes | no | no |

## Privacy and cost
- There is no server. Your key and adventures live in your browser's storage (plus an optional folder you choose). The key is sent only to the API endpoint in Settings, and is never written to adventure files.
- Do not enter your key on a shared computer. Use a key with a low spending cap.
- Chrome and Edge send dictation audio to Google or Microsoft for transcription.
- You pay your provider per call. The bar above the message box estimates cost per turn and per adventure; check the prices in *Settings > Story & cost*.

## Troubleshooting
- **"Model not found" or a 404:** preview models get renamed. Open *Settings > Connection*, press **Test connection & list models**, and pick an available model.
- **401 or 403:** the key was not accepted. Re-paste it.
- **429:** rate limit or daily quota. Wait, or switch the voice engine to the free browser voice.
- **Browser storage is full:** export a backup, or link a save folder in *Settings > Data*.

## License
MIT. See `LICENSE`.
