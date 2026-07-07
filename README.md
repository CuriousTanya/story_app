# Story Time 🦉

A bedtime-story generator built for the car, the couch, or anywhere your kid wants a story read aloud.

**🔗 Try it now: [kidsllmstory.netlify.app](https://kidsllmstory.netlify.app)** — no setup needed to try it, but you'll still need your own free API key (see below) to generate stories.

Pick a hero, an adventure, and a mood — the app designs a story plan, writes the story, checks it for safety and quality, then narrates it out loud. No app store, no sign-up walls: it's a single HTML file you host yourself.

## How it works

1. **Story Planner + Writer** — one AI call designs a story blueprint (goal, obstacle, emotional arc, lesson, twist, ending) and writes the full story following that plan.
2. **Critic** — a second AI call scores the story on safety, engagement, and emotional arc. If it doesn't pass, the app automatically rewrites it (up to 3 tries) before showing anything.
3. **Narration** — the finished story is read aloud using a free, natural-sounding voice.

Everything runs entirely in your browser. Your API keys are stored only on your device (`localStorage`) — nothing is sent to any server except Google's and (optionally) ElevenLabs'.

## Setup

You need one free API key to get started. A second one is optional for higher-quality voices.

### 1. Get a free Google Gemini API key (required)

This powers the story writing and safety/quality checks.

1. Go to **[aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)**
2. Sign in with any Google account
3. Click **Get API Key** → **Create API Key**
4. Copy the key (starts with `AIza...`)

No credit card required. The free tier is generous enough for regular story-time use.

### 2. Narration voice — works out of the box, no key needed

The app uses [Puter.js](https://puter.com) to generate natural-sounding narration for free, with no signup and no key. This is the default and works immediately.

### 3. (Optional) ElevenLabs key — for premium voice quality

If you want an even more natural narrator voice:

1. Go to **[elevenlabs.io](https://elevenlabs.io)** and sign up free
2. Go to **Developers → API Keys → Create API Key**
3. Make sure **Text to Speech** scope is enabled
4. Copy the key

The free ElevenLabs tier is limited (~10,000 characters/month, roughly 2–3 stories), so it's optional. Leave it blank to just use the free Puter.js voice.

### 4. Deploy the app

The app is a single `index.html` file — deploy it anywhere that serves static files. Two easy options:

**Option A — GitHub Pages (free, permanent link)**
1. In this repo, go to **Settings → Pages**
2. Under "Source", choose the `main` branch and `/ (root)` folder
3. Save — GitHub will give you a URL like `https://curioustanya.github.io/story_app/`

**Option B — Netlify Drop (fastest, no account needed)**
1. Go to **[app.netlify.com/drop](https://app.netlify.com/drop)**
2. Drag `index.html` onto the page
3. You'll get an instant live URL

### 5. Add to your phone's home screen

1. Open your deployed URL in **Safari** (iPhone) or **Chrome** (Android)
2. Tap the Share button → **Add to Home Screen**
3. It now behaves like a regular app icon — tap to open, no browser bar

### 6. First launch

- Paste your Gemini key
- Optionally paste an ElevenLabs key, or leave blank for the free voice
- Tap **Test & Save Keys** — you should hear a short voice sample
- You're ready to go

Keys are saved on your device only, so you only do this once per device.

## Using the app

1. Pick a **hero** or type your own companion
2. Pick an **adventure type** and a **mood**
3. Optionally open **Parent Settings** to set age, story length, a lesson/development goal (persistence, confidence, kindness, etc.), and how scary the story can be
4. Tap **Tell Me a Story ✨**
5. Tap the play button once the story is ready — it narrates automatically, with pause/resume/replay controls

Every story shows safety, fun, and emotional-arc scores, plus a collapsible "Story Blueprint" section for parents who want to see what the story is teaching.

## Safety design

- A keyword blocklist scans every generated story before it's shown
- A second AI pass scores safety and quality; stories below the threshold are automatically rewritten
- Scary level is parent-controlled (None / A little / Some)
- No login, no ads, no data collection — everything stays on your device

## Costs

- **Google Gemini**: free tier, no credit card
- **Puter.js voice**: free, no key
- **ElevenLabs** (optional): free tier ~2–3 stories/month, paid plans available if you want more

## Tech notes

Single-file vanilla JavaScript app — no build step, no framework, no dependencies beyond two CDN scripts (Google Fonts, Puter.js). Works in any modern browser. State and API keys persist via `localStorage`.

## License

MIT — see [LICENSE](LICENSE).
