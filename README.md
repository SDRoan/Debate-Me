# Debate Me

`Debate Me` is a bold, single-file web app where users type an opinion and an AI opponent argues back in a Gen-Z-style voice.

Built with plain `HTML`, `CSS`, and `JavaScript` using local `Ollama` (no frameworks, no npm).

## Features

- Multi-turn debate flow
- AI opponent with playful Gen-Z tone
- `Trending Topics` starter ideas fetched from internet (Wikimedia most-read pages)
- One-click topic chips to auto-fill debate prompts
- Live scoreboard (`You` vs `Counter Cannon`)
- `End Debate` winner/loser verdict with round summary
- `Try Another` to reset and start fresh

## Tech Stack

- Frontend: single `index.html`
- AI: `Ollama` local API (`http://127.0.0.1:11434/api/generate`)
- Model default: `llama3.2`
- Trend source: Wikimedia Pageviews Top API

## Prerequisites

- macOS/Linux/Windows terminal
- `Python 3`
- `Ollama` installed

## Run Locally

1. Start a local static server from this project folder:

```bash
cd "/Users/saibyasachiruhan/Desktop/Debate me"
python3 -m http.server 5502
```

2. In another terminal, start Ollama:

```bash
ollama serve
```

3. Pull the model (first time only):

```bash
ollama pull llama3.2
```

4. Open in browser:

```text
http://localhost:5502
```

## How to Use

1. Type your opinion, or click a trending topic chip to prefill one.
2. Click `Debate Me`.
3. Continue the back-and-forth with `Send Rebuttal`.
4. Click `End Debate` anytime to declare winner/loser.
5. Click `Try Another` to reset the session.

## Config (Optional)

Inside `index.html`, you can tune:

- `MODEL_NAME` (default: `llama3.2`)
- `MAX_USER_TURNS` (default: `8`)
- Prompt behavior/style in `buildDebatePrompt()`

## Troubleshooting

- `Cannot reach Ollama at http://127.0.0.1:11434`
  - Run `ollama serve`
- `model is missing`
  - Run `ollama pull llama3.2`
- `Address already in use` when running Python server
  - Use another port, e.g. `python3 -m http.server 5503`
- Trending date shows yesterday
  - Wikimedia daily feed can lag; app shows local today and latest available source date

## Notes

- This app is intentionally frontend-only + local Ollama.
- If you host this on static hosting, Ollama calls will not work unless you provide a backend/proxy.
