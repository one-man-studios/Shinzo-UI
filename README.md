# Shinzo-UI
A robust, single standalone html file AI interface for Ollama and OpenAI. Features local RAG with vector search, real-time voice/video calls, document analysis (PDF/DOCX), and project workspaces. Runs entirely in the browser using IndexedDB for privacy and speed—no external backend required.

## How to use
* Just download the html file
* Configure the API, if u have OpenAI's API or Setup Base URL if u use Ollama or Llama.cpp
* Then you're good to go.
* Have fun prompting.

## Highlights

- **100% client-side** — the entire app is one HTML file with inline CSS/JS
- **Local-first storage** — all chats, documents, and settings are saved in `localStorage` (with automatic one-time migration from an older IndexedDB version); no telemetry, analytics, or external data collection
- **Bring your own backend** — connects to Ollama, a local llama.cpp/KoboldCpp server, or any OpenAI-compatible API
- **In-browser embeddings** — Transformers.js running on WebGPU/WASM for local RAG, no external embedding API needed

## Features

| Tab | Description |
|---|---|
| 💬 Chat | Main conversation interface, streaming responses, image attachments, persona/character support |
| 🗄️ Knowledge Base | Upload and manage documents for retrieval-augmented generation |
| 🗂️ RAG Spaces | Group documents into named retrieval spaces |
| 🚀 Spaces | Project-style workspaces with linked files, links, instructions, and dedicated chat history |
| 📚 Prompt Library | Save, browse, and reuse prompt templates with `{{variable}}` placeholders |
| 🧱 Model Builder | Configure and customize model presets |
| 🕸️ Graph | Visual/graph-based view (D3.js) |
| 🛠️ Offline Tools | Summarizer, flashcard generator, translator, code explainer, and writing assistant — all run through your configured model |
| ⚙️ Settings | Backend connection, chat behavior, persona/World Info, storage stats, and theming |

### Offline Tools in detail

- **Summarizer** — bullet/paragraph/TL;DR/ELI5/academic styles, adjustable length
- **Flashcard generator** — produces study cards from notes, with a flip-card study mode and CSV export
- **Translator** — translate text with selectable tone/style, including custom target languages
- **Code assistant** — explain, review, optimize, document, test, or debug code
- **Writing assistant** — improve clarity, fix grammar, adjust tone (formal/casual), shorten, expand, or continue text

Each tool's output can be sent directly into the Chat tab for follow-up.

## Supported backends

Configured in **Settings → API URL / Backend Type**:

| Backend | Default endpoint pattern |
|---|---|
| Ollama | `http://localhost:11434` (`/api/tags`, `/api/chat`) |
| Local Server (llama.cpp / KoboldCpp) | `/api/v1/model`, `/api/v1/generate` |
| OpenAI-compatible | `/v1/models`, `/v1/chat/completions` |

The app auto-detects available models from the connected backend and shows a live connection status indicator.

## Getting started

1. Download `shinzo_ui_v5.html`.
2. Open it directly in a modern browser (Chrome/Edge recommended for WebGPU support), or serve it via any static file server.
3. Start your local LLM backend (e.g. `ollama serve`, or a llama.cpp/KoboldCpp/OpenAI-compatible server).
4. Go to **Settings**, enter the API URL and backend type, and select a model.
5. Start chatting.

No installation, build tools, or package manager required.

## Data & privacy

- All chat history, documents, personas, and settings are stored in your browser's `localStorage`.
- Nothing is sent anywhere except the LLM API endpoint you configure yourself.
- Storage usage is visible under **Settings → Privacy/Storage**, along with counts of chats, messages, and documents.
- Because `localStorage` has a practical size limit (typically ~5–10MB per origin, browser-dependent), very large chat histories or document sets may hit quota limits — the app will warn on write failures.

## Tech stack

Loaded via CDN, no bundler:

- [marked](https://github.com/markedjs/marked) + [DOMPurify](https://github.com/cure53/DOMPurify) — Markdown rendering
- [KaTeX](https://katex.org/) — math rendering
- [Mermaid](https://mermaid.js.org/) — diagrams
- [PDF.js](https://mozilla.github.io/pdf.js/) — PDF parsing
- [Mammoth.js](https://github.com/mwilliamson/mammoth.js) — `.docx` parsing
- [D3.js](https://d3js.org/) — graph visualization

## Themes

Includes multiple built-in color themes (default dark, Mocha, Discord, Matrix, Purple, and others), switchable from Settings and persisted across sessions.

## License

Created by [One Man Studios](https://github.com/one-man-studios)

This project is provided as-is for educational and personal use. Commercial use is strictly prohibited.

## Contributing

Feel free to:
1. Fork the repository
2. Give a star rating 🌟
3. Submit pull requests

**Note**: This is a client-side application. All processing happens in your browser. No data is sent to external servers unless explicitly configured in settings.
