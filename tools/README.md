# Æsethien — Sharon's Vocabulary Guide

## Your workflow in 4 steps

### Step 1 — Add words to the spreadsheet

Open `data/aesethien-vocab.xlsx`

Go to the **Vocabulary** sheet. Fill in two columns only:

| Column A | Column B |
|----------|----------|
| Room name | German word (noun only, no article) |
| Markthalle | Kartoffel |
| Depot | Schere |

**Room names to use exactly:**
- `Markthalle`
- `Depot`
- `Kernarchiv`
- `Ankunftsbahnsteig`
- `Haengegaerten`
- `Ratssaal`

Save the file.

---

### Step 2 — Run the pipeline (first time only: install dependencies)

Open a terminal (Windows: press Win+R, type `cmd`, press Enter).

Navigate to the repo:
```
cd C:\Users\91942\Documents\GitHub\aesethia-awaits
```

First time only — install Python packages:
```
pip install -r tools/requirements.txt
```

Then run:
```
python tools/enrich.py
```

The script will:
- Look up every word on Wiktionary (article, plural, English, pronunciation, audio)
- Download pronunciation audio files
- Download icons from Noun Project (if API keys are set)
- Write JSON files to `public/vocab/data/`
- Update your spreadsheet with the enriched data

---

### Step 3 — Check the result

Open `public/vocab/index.html` in your browser to preview the rooms locally.

---

### Step 4 — Push to GitHub

Open **GitHub Desktop**.

You'll see your changed files listed. Write a short message like:
> Added Kartoffel and Schere to Depot

Click **Commit to master** → then **Push origin**.

Done — live within 60 seconds at:
`https://sirnetizen.github.io/aesethien-world/vocab/`

---

## Noun Project API keys (optional but recommended for clean icons)

1. Go to [thenounproject.com/developers](https://thenounproject.com/developers/)
2. Create a free account
3. Create an app — copy the **Key** and **Secret**
4. Open the `.env` file in the repo root and add:

```
NOUN_PROJECT_KEY=paste_your_key_here
NOUN_PROJECT_SECRET=paste_your_secret_here
```

Without these keys, the rooms show emoji instead of icons. Everything else still works.

---

## Troubleshooting

**"python is not recognized"** — Install Python from [python.org](https://python.org). Tick "Add to PATH" during install.

**"No module named openpyxl"** — Run `pip install -r tools/requirements.txt` again.

**A word has wrong article/meaning** — Edit `public/vocab/data/{room}.json` directly and correct it. Push the change. Wiktionary is usually right but not always.

**Audio not playing** — The browser will fall back to text-to-speech (German voice) if the audio file is missing. Not ideal but functional.
