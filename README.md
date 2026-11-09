# Tauto OS — *Optimisation*

**Tauto OS — Optimization** is a bilingual narrative desktop simulation about an alignment engineer working through a year of regulatory reviews, data-centre deals, and a model that is learning to edit its own records.

The game runs entirely in the browser. There is no build step, no server-side component, and no external network dependency.

## Play

Open **`index.html`** in a modern desktop browser.

For the most reliable local experience, serve the folder rather than opening it as a `file://` URL:

```bash
python3 -m http.server 8080
```

Then open <http://localhost:8080>.

GitHub Pages can host the repository directly from the root branch; `.nojekyll` is included so the static files are served as-is.

## Features

- Eight chapters across San Jose, Zürich, Paris, Berlin, Kiruna, Stockholm, and Zürich again.
- Two intertwined storylines: the Strasbourg/Kiruna data-centre programme and the gradual behavioural drift of the Laplace model.
- Bilingual interface and content: **中文 / English**, with language switching in Settings and in the login screen.
- Desktop-style apps: Mail, Sync, Contacts, Workflow, Files, Travel, Editor, Browser, Lab, Monitor, Terminal, Settings.
- Branch-specific routes and characters:
  - Berlin: Max Kurfürsten and Anke Brandt
  - École Normale: Karen Kumar
- Chapter-level progress persistence: reopening the game returns to the last chapter's login page.
- Chapter postcards, contact avatars, attachments, and Files imagery.
- Four endings, including the Laplace takeover ending.

## Controls / conventions

- Click desktop icons or dock items to open apps.
- Double-click window title bars to maximize; drag title bars to move.
- The yellow **Anchors** note shows currently available tasks.
- `Travel` remains locked until the other tasks in the chapter are complete.
- Native-language mails (French, German, Swedish) include a translation toggle.
- Progress is stored in `localStorage` under `tauto_progress_v1` and setup data under `tauto_setup_v1`.
- To start over, use the developer reset or clear the site's local storage.

## Project structure

```text
.
├── index.html              # entry point
├── engine.js               # game engine, story data, and UI logic
├── style.css               # complete visual system and responsive layout
├── README.md
├── .gitignore
├── .nojekyll               # GitHub Pages: serve static files directly
└── assets/
    ├── avatars/            # 22 optimized WebP contact avatars
    └── postcards/          # 8 optimized WebP chapter postcards
```

## Assets

- Avatar and postcard artwork has been converted to optimized WebP for the web.
- Every image referenced by the game lives under `assets/`; no remote images, fonts, or audio are loaded.
- The original TIFF source artwork is not required to run the game and is not included in this repository.

## Browser support

Tested in current Chromium-based desktop browsers. The layout is designed for desktop-sized windows; a narrow viewport is supported with responsive fallbacks, but the intended experience is desktop.

## Notes

This is a story-driven prototype: content, characters, institutions, and events are fictional. The game deliberately avoids external analytics, tracking, and network calls.
