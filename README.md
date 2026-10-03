# Holodeck

A single-file, AI-run text adventure. Answer 11 quick questions and a Game Master builds a story just for you, remembers everything, steers toward a real ending, and grades the result with a report card. Play by typing or hands-free by voice, in English or Spanish.

<!-- Add a screenshot here: ![Holodeck](screenshot.png) -->

## Features
- **Curated start:** 11 questions (length, genre, vibe, character, hook) shape your world. Pick a romantic vibe and a final question asks who you are and who you're interested in.
- **Short stories that read like short stories:** 5 and 10 turn adventures are told clean and simple (one goal, a small cast, a payoff ending), and their suggested settings stay on Earth in familiar times.
- **Same cast, new story:** after a story you love, start a sequel, a "years later", a fresh start or a prequel with the same characters and world.
- **Long-term memory:** story bible, lorebook, chapter summaries and hybrid keyword + semantic recall keep long stories consistent.
- **A plan behind the curtain:** secret roadmap, hidden GM secrets, and a "director" that varies pacing and flags repeated phrases.
- **Report card:** story grade, play grade, and a review of the secret roadmap at the end.
- **Hands-free voice:** dictation (say *make it so*, or *que así sea* in Spanish, to send), narrator voice, soft background sound, and automatic cleanup of misheard words.
- **English or Spanish:** menus, questions, narration, voices and the send phrase all switch (Settings, the start screen, or the EN/ES button in the header).
- **You stay in control:** edit the bible and lore mid-story (your edits win over earlier narration), undo a turn (memory included), watch the cost meter, save adventures as plain JSON files.

## Quick start
1. Pick an AI provider and get an API key (see below). Google Gemini has a free tier.
2. Open the app (see below), choose the provider on the welcome screen and paste the key.
3. Press **Save key and start**.

No key yet? Choose **Try the offline demo** to look around with a fake Game Master.

### AI providers
| Provider | Get a key | Narrator voice | Smart memory (embeddings) |
|---|---|---|---|
| Google Gemini | https://aistudio.google.com/apikey (free tier) | yes | yes |
| OpenAI (ChatGPT models) | https://platform.openai.com/api-keys | yes | yes |
| Anthropic (Claude) | https://console.anthropic.com/settings/keys | browser voice | keyword memory |
| xAI (Grok) | https://console.x.ai | browser voice | keyword memory |
| Other (OpenAI-compatible) | e.g. OpenRouter, https://openrouter.ai/keys (one key for many models) | browser voice | if the endpoint has one |

A ChatGPT Plus or Claude.ai subscription does **not** include API access: you need a separate API key with billing from the provider's developer site. Each provider keeps its own key, so you can switch back and forth.

**Free Gemini keys:** the free tier does not include the Pro story model. The app detects this on the first refusal (or when you press **Test connection**) and runs the story on the cheap Flash model instead. Paid keys keep the Pro default.

### Running it
- **Hosted:** rename `holodeck-optimized.html` to `index.html`, push to a GitHub repo, and enable *Settings > Pages* (deploy from the main branch). Share the link; every player brings their own key.
- **Locally:** from the folder, run `python3 -m http.server 8080` and open `http://localhost:8080/holodeck-optimized.html`. (Opening the file directly works, but browsers then re-ask for microphone permission every time.)

### Browsers
| Browser | Typing | Dictation | Save to folder |
|---|---|---|---|
| Chrome / Edge | yes | yes | yes |
| Safari (Mac, iPhone, iPad) | yes | yes | no (use Export / Import) |
| Firefox | yes | no | no |

On iPhone and iPad, the narrator starts after your first tap anywhere on the page (Safari's rule for sound). If it ever waits, a line asks you to tap once.

**Backup voice on iPhone and iPad:** when the AI narrator is unavailable or out of credits, the app falls back to the device's voices. Web pages on iPhone and iPad can only use Apple's basic built-in voices (Enhanced or Premium voices downloaded in *Settings > Accessibility > Read & Speak > Voices* are not available to Safari), so the backup voice sounds robotic there. The app picks the best one it can. If Safari stays silent, a line asks you to tap once and the reply is read on that tap.

**Narrator voice quota:** by default the app makes one voice request per reply (the voice starts once the reply is written), so a daily limit such as Gemini's ~100 requests lasts about 100 replies. *Settings > Voice & sound* trades more requests for a quicker start.

## Privacy and cost
- There is no server. Your key and adventures live in your browser's storage (plus an optional folder you choose). The key is sent only to the provider you picked, and is never written to adventure files.
- Do not enter your key on a shared computer. Use a key with a low spending cap.
- Chrome and Edge send dictation audio to Google or Microsoft for transcription.
- You pay your provider per call. The bar above the message box estimates cost per turn and per adventure (including input the provider served from its cache at a discount); each provider has its own default prices in *Settings > Story & cost*, so check them against your billing page.
- Built to keep costs down: the story model thinks at *Low* effort by default, the hidden plot notes and all memory work run on the cheap model, recalled memories are short excerpts, and the prompt is laid out so most of it repeats each turn and can be billed as cached input. Raise the thinking effort in *Settings > Story & cost* if you want deeper (slower, pricier) replies.

## Troubleshooting
- **"Model not found" or a 404:** models get renamed. Open *Settings > Connection* and press **Test connection & list models**: it lists what your key can use and switches to available models if a default is missing.
- **401 or 403:** the key was not accepted. Re-paste it, and check the provider matches the key.
- **429:** rate limit or daily quota. Wait, or switch the voice engine to the free browser voice.
- **"Could not reach ... (CORS)":** some endpoints do not accept requests from web pages. Try OpenRouter, which does.
- **Browser storage is full:** export a backup, or link a save folder in *Settings > Data*.

## License
MIT. See `LICENSE`.
