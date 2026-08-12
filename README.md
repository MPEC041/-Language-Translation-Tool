# Voice & Text Translator — Two Implementations

Both do the same three jobs:
1. **Voice → Text → Translated text**
2. **Text → Translated text**
3. **Voice → Voice** (speak, and hear the translation spoken back to you)

## 1. Web version (`index.html`)

A single self-contained HTML file — no install, no server needed.

**Run:** just open `index.html` in Chrome, Edge, or Safari (double-click it, or drag it into the browser).

- **Voice → Text tab:** click the mic, allow microphone access, speak. It transcribes and translates automatically.
- **Text → Text tab:** type or paste text, pick languages, click Translate.
- **Voice → Voice tab:** click the mic, speak, and the translation is read aloud automatically using the browser's speech synthesis. Use "Replay spoken translation" to hear it again.

Voice recognition and speech synthesis use the browser's built-in Web Speech API (Chrome/Edge/Safari only — Firefox doesn't support speech recognition yet). Translation in both versions uses free translation services (Google Translate via `deep-translator` in Python, MyMemory API in the web version) — an internet connection is required for translation either way.
