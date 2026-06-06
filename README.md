# 🌿 Bot Marley

A chatbot inspired by the spirit, values, and life philosophy of Bob Marley and the Rastafari movement — built as a learning project, 100% in the browser (HTML + JS + Claude API), no backend required.

## How it works

- It's a single page (`index.html`) that runs entirely in your browser.
- It uses Anthropic's [Claude API](https://docs.claude.com) to generate responses in real time.
- A *system prompt* gives Claude the "Marley personality": warmth, unity, hope, resilience, nature, justice, and joy — expressed in its own words, plus a song recommendation at the end of every reply.
- Your API key is stored only in your browser's `localStorage`. It's never sent to any server of ours (there is no backend) — it travels directly from your browser to Anthropic's API.

## How to use it

1. Get an API key at [console.anthropic.com](https://console.anthropic.com/) (Settings → API Keys).
2. Open `index.html` in your browser (double-click it, or publish it on GitHub Pages — see below).
3. Paste your API key into the field at the top and press **Save**.
4. Start chatting!

## Publishing it on GitHub Pages

1. Create a new repository on GitHub and upload `index.html` (and this `README.md`).
2. Go to **Settings → Pages**, select the `main` branch and the root folder (`/`).
3. GitHub will give you a public URL (something like `https://your-username.github.io/bot-marley/`).
4. Share the link — everyone who visits uses **their own** API key, stored only in their own browser.

## About the lyrics and copyright

This project **does not contain or reproduce Bob Marley song lyrics**. The *system prompt* explicitly instructs the model to:

- speak in its own voice, drawing on the themes and spirit associated with Bob Marley (unity, hope, nature, peaceful resistance, joy),
- mention song **titles** when relevant,
- but **never** reproduce verses, stanzas, or extended lyric fragments — not even close paraphrases — limiting itself to, at most, very short and widely known phrases woven naturally into its own sentences.

This is an unofficial, educational project with no affiliation to the Marley family, their record labels, or rights holders. All trademarks and names mentioned belong to their respective owners.

## Technical / cost notes

- Model used: `claude-haiku-4-5` (fast and cost-effective).
- `max_tokens` is capped at 450 per response, and the conversation history is trimmed to the last 12 messages, to keep API costs predictable.
- The request includes the `anthropic-dangerous-direct-browser-access: true` header, required to call the Anthropic API directly from the browser (instead of from a server). Keep in mind this exposes your API key client-side — that's why each person uses their own, and you should never share yours.

## License

Open source for educational purposes. Use it, modify it, and share it freely — just remember not to include copyrighted material (like full song lyrics) in your own versions.
