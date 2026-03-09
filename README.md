# Æsethien — A German Language World

> *Enter the world. Solve the missions. Speak German.*

**Jacob & Schiffer GbR — MitMut Studio, Berlin**

---

## What's in this repo

```
aesethien-world/
├── public/vocab/        ← Interactive vocabulary rooms (live on GitHub Pages)
│   ├── index.html       ← Room selector
│   ├── room.html        ← Interactive room viewer with popups + quiz
│   └── data/            ← Enriched vocab JSON (one file per room)
├── data/                ← Sharon's vocabulary spreadsheet
├── tools/               ← Sharon's enrichment pipeline
│   ├── enrich.py        ← Main script: xlsx → Wiktionary → Noun Project → JSON
│   └── README.md        ← Sharon's plain-English guide
├── maps/                ← Tiled map files (.tmj) for WorkAdventure
├── src/                 ← WorkAdventure TypeScript scripts
└── .env.example         ← API key template (copy to .env, never commit .env)
```

## Live URLs

| What | URL |
|------|-----|
| Vocab rooms | https://sirnetizen.github.io/aesethien-world/vocab/ |
| Markthalle room | https://sirnetizen.github.io/aesethien-world/vocab/room.html?room=Markthalle |
| Depot room | https://sirnetizen.github.io/aesethien-world/vocab/room.html?room=Depot |
| Kernarchiv room | https://sirnetizen.github.io/aesethien-world/vocab/room.html?room=Kernarchiv |

## Sharon's workflow

See `tools/README.md` — add words to the spreadsheet, run `python tools/enrich.py`, push.

## Stack

- **Vocab world:** Vanilla HTML/CSS/JS — no framework, no build step, works anywhere
- **Data pipeline:** Python (requests, openpyxl, requests-oauthlib)
- **APIs:** Wiktionary (free, no key), Noun Project (free tier, key needed for icons)
- **Hosting:** GitHub Pages (free)
- **Live world:** WorkAdventure (free tier, 15 concurrent users)
- **State persistence:** Supabase (Phase 2)

## Contact

hallo@mitmut.de · mitmut.de
