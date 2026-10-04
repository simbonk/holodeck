# Holodeck

A single-file, AI-run text adventure powered by Google Gemini. Say how much time you have and the feeling you want, pick a curated story or a plot-free experience (or just upload a photo), and a Game Master builds a world just for you, keeps an eye on the clock, lands a real ending, and grades the result with a report card. Play by typing or hands-free by voice.

<!-- Add a screenshot here: ![Holodeck](screenshot.png) -->

## Features
- **Play by the clock, not by turns:** choose 10 minutes to 2 hours. The app learns your pace, estimates how many replies are left, starts wrapping up about three replies from the end, and lands a storybook ending in time. Having fun? **+10 min** in the header stretches the session.
- **The feeling comes first:** pick the feeling you want (Nostalgia, Unapologetic Relaxation, Exhilaration and Adventure, Deep Connection Love, Pure Indulgence, Awe and Wonder, or your own words; more suggestions appear while you think). It goes into the bible and is the Game Master's main goal.
- **It notices when you're happy:** every turn the memory pass also reads your mood. When the feeling is landing or you are clearly enjoying a character or place, the plot steps aside: no interruptions, no new complications, and threats don't follow you 200 light years away. Walk away from the plot and it lets you go.
- **Two ways to play:** a *curated story* (a hidden roadmap timed to the session, which bends or waits for you) or an *experience simulator* (no plot points at all: a richly painted world, your own goal, and the feeling).
- **Personal details:** your name, gender and who you're interested in (both free text, in your own words) and your birth year live in *Settings > Personal details* and are filled in for every new experience (change them for any one story). The romance answer also picks the narrator: Sulafat if you're interested in women, Charon if men.
- **Paint the world from a photo:** upload a picture and the holodeck works out the place, the time and the people, writes a detailed description of the world, adds lore, and fills in the rest of the questions.
- **Living lore:** when something changes in play (a relationship, a location, a secret revealed), the lore entry is updated, with earlier versions kept in the Lore tab. It rides on the existing memory call, so it costs no extra requests.
- **Short sessions that read like short stories:** 15 minutes or less is told clean and simple (one goal, a small cast, a payoff ending), and its suggested settings stay on Earth in familiar times.
- **Same cast, new story:** after a story you love, start a sequel, a "years later", a fresh start or a prequel with the same characters and world.
- **Long-term memory:** story bible, lorebook, chapter summaries and hybrid keyword + semantic recall keep long stories consistent.
- **A plan behind the curtain:** secret roadmap, hidden GM secrets, and a "director" that varies pacing and flags repeated phrases.
- **Report card:** two grades from a discerning high school teacher: *How the Holodeck did* (did it deliver the feeling and your goals?) and *How you did* (your own choices and play).
- **Hands-free voice:** dictation (say *make it so* to send; the phrase glows while the mic listens), Gemini narrator voice, soft background sound, and automatic cleanup of misheard words.
- **You stay in control:** edit the bible and lore mid-story (your edits win over earlier narration), undo a turn (memory included), watch the cost meter, save adventures as plain JSON files.

## Quick start
1. Get a free Gemini API key: https://aistudio.google.com/apikey
2. Open the app (see below) and paste the key on the welcome screen.
3. Press **Save key and start**.

No key yet? Choose **Try the offline demo** to look around with a fake Game Master.

**Free keys:** Google's free tier does not include the Pro story model. The app detects this on the first refusal (or when you press **Test connection**) and runs the story on the Flash model instead. Paid keys keep the Pro default.

### Running it
- **Hosted:** rename `holodeck-optimized.html` to `index.html`, push to a GitHub repo, and enable *Settings > Pages* (deploy from the main branch). Share the link; every player brings their own key.
- **Locally:** from the folder, run `python3 -m http.server 8080` and open `http://localhost:8080/holodeck-optimized.html`. (Opening the file directly works, but browsers then re-ask for microphone permission every time.)

### Browsers
| Browser | Typing | Dictation | Save to folder |
|---|---|---|---|
| Chrome / Edge | yes | yes | yes |
| Safari (Mac, iPhone, iPad) | yes | yes | no (use Export / Import) |
| Firefox | yes | no | no |

**iPhone and iPad:** the Gemini narrator starts after your first tap anywhere on the page (Safari's rule for sound). When the Gemini voice is out of quota, the app falls back to Safari's own default voice; web pages can only use Apple's basic built-in voices (downloaded Enhanced or Premium voices are not available to Safari), so it sounds robotic. If Safari ever stays silent, a line asks you to tap once and the reply is read on that tap.

**Hear nothing from the device voice on iPhone or iPad? Check Silent Mode.** It mutes the device voice and the background sounds, while the Gemini voice still plays. To turn it off, swipe down from the top-right corner of the screen to open Control Center and tap the bell so it is no longer crossed out. Older iPads and iPhones may have a switch on the side instead (orange showing means silent); newer iPhones can also use the Action button. *Settings > Voice & sound > Test device voice only* checks it.

**Narrator voice quota:** by default the app makes one voice request per reply (the voice starts once the reply is written), so a daily limit such as ~100 voice requests lasts about 100 replies. *Settings > Voice & sound* trades more requests for a quicker start.

## Privacy and cost
- There is no server. Your key and adventures live in your browser's storage (plus an optional folder you choose). The key is sent only to Google, and is never written to adventure files.
- Do not enter your key on a shared computer. Use a key with a low spending cap.
- Chrome and Edge send dictation audio to Google or Microsoft for transcription.
- You pay Google per call. The bar above the message box estimates cost per turn and per adventure (including input Google served from its cache at a discount); check the prices in *Settings > Story & cost* against your billing page.
- Built to keep costs down: the story model thinks at *Low* effort by default, the hidden plot notes and all memory work run on the cheap model, recalled memories are short excerpts, and the prompt is laid out so most of it repeats each turn and can be billed as cached input. Raise the thinking effort in *Settings > Story & cost* if you want deeper (slower, pricier) replies.

## Troubleshooting
- **"Model not found" or a 404:** preview models get renamed. Open *Settings > Connection* and press **Test connection & list models**: it lists what your key can use and switches to available models if a default is missing.
- **401 or 403:** the key was not accepted. Re-paste it.
- **429:** rate limit or daily quota. Wait, or switch the voice engine to the free browser voice.
- **Browser storage is full:** export a backup, or link a save folder in *Settings > Data*.

## License
MIT. See `LICENSE`.
