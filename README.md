# Holodeck (Optimized)

An immersive, AI-powered text adventure engine built entirely into a single HTML file. 

Holodeck acts as a dynamic Game Master, generating responsive, open-ended interactive fiction based on a player's customized world-building choices. It runs entirely in the browser without requiring a dedicated backend server.

## Features
* **Zero-Install Portability:** The entire application (HTML, CSS, JavaScript) is bundled into a single file. 
* **Bring Your Own LLM:** Compatible with OpenAI-format endpoints, allowing you to plug in your own API key to drive the Game Master.
* **Persistent Local Memory:** Uses your browser's local storage and IndexedDB to save adventure progress, story bibles, and generated lore.
* **Hybrid Recall System:** Features client-side BM25 keyword retrieval and semantic embeddings to keep the AI contextually aware of past events without overflowing the token window.
* **Voice Integration:** Supports hands-free microphone dictation and text-to-speech (TTS) narration for a fully immersive experience.
* **Director Mode:** A hidden pacing system that subtly nudges the AI to introduce complications, emotional beats, or sensory details to keep the narrative engaging.

## Quick Start
1. Download or clone `holodeck-optimized.html`.
2. Open the file directly in any modern web browser (Chrome, Edge, or Safari recommended for voice features).
   * *Note: For the best experience with local saving and microphone permissions, serve the file via a lightweight local web server (e.g., `npx serve` or python's `http.server`) rather than opening it directly from the file system.*
3. Click **Settings** to input your OpenAI-compatible API key and configure your preferred models (Story model vs. Cheap model for background tasks).
4. Click **Set up a new experience** to define your world, character, and genre.

## Privacy & Security
Your API key is stored strictly in your browser's `localStorage` and is only sent directly to the AI endpoint you specify. It is never transmitted to any other third-party servers or saved in the exported adventure files.