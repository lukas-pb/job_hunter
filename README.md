# Job Hunter — Data & AI Market Explorer

A single-file browser tool for exploring the Australian Data & AI job market in real time, powered by the [Adzuna API](https://developer.adzuna.com/).

No server. No install. No Python. Open the page, enter your API key, and go.

**Built with [Claude](https://claude.ai) by Anthropic.**

---

## Live demo

**[→ Open the app](https://lukas-pb.github.io/job_hunter)**

---

## What it does

Job Hunter fetches live job listings across configurable Data & AI search segments and gives you two views:

**Skill demand heatmap** — shows how often each technical skill appears across job descriptions, broken down by segment. Useful for spotting which tools employers are actually asking for right now vs. what the internet says you should learn.

**Ranked jobs table** — every listing scored and sorted by how well it matches a target stack. Python and SQL score +3 points each as core skills; secondary tools like Databricks, dbt, Airflow, and cloud platforms score +1 each. Duplicates are removed — if the same role appeared across multiple search segments it only shows once, with all matching segments noted. Filter by keyword, segment, or sort by salary.

Both the skill list and scoring stack are fully customisable from the Settings tab — no code editing required.

---

## Getting started

### 1. Get a free Adzuna API key

Go to [developer.adzuna.com](https://developer.adzuna.com/signup) and sign up — it's free and takes about two minutes. You'll receive an **App ID** and an **App Key**.

### 2. Open the app

Visit the GitHub Pages link above, or download `index.html` and open it directly in any browser.

### 3. Configure and fetch

- Enter your **App ID** and **App Key** in the bar at the top of the page
- Select a **city** from the sidebar (Brisbane, Sydney, Melbourne, Perth, Adelaide, Canberra)
- Toggle which **segments** you want to include
- Set **pages** — each page returns up to 50 jobs, so pages=2 gives up to 100 jobs per segment
- Hit **Fetch jobs**

Results load in 30–60 seconds depending on how many segments and pages you selected.

---

## Customising

Everything is configurable from the **Settings** tab — no need to touch the HTML file.

| Setting | What it does |
|---|---|
| Search segments | The job titles queried on Adzuna. Add custom ones like "analytics engineer", remove ones you don't care about. |
| Tracked skills | Keywords scanned in job descriptions to build the heatmap. |
| Core skills (+3 pts) | Your must-haves. Jobs mentioning these rank much higher. |
| Secondary skills (+1 pt) | Nice-to-haves that bump up the ranking. |

All changes take effect on the next fetch. Each section has a reset button to restore defaults.

---

## Default segments

| Segment | What it captures |
|---|---|
| Business Intelligence | BI developers, analysts, reporting roles |
| Data Analyst | General analytics, insights, dashboards |
| Data Scientist | Modelling, statistics, research-heavy roles |
| Machine Learning Engineer | ML pipelines, model deployment, MLOps |
| Data Engineer | Pipelines, warehousing, infrastructure |
| AI Engineer | LLMs, generative AI, applied AI products |

---

## Exporting results

Click **Export CSV** in the Ranked Jobs tab to download all matching jobs with their scores, matched skills, salary data, and links. The filename includes the city and date so exports from different sessions don't overwrite each other.

---

## Notes

- The Adzuna API is free with generous limits for personal use. See their [docs](https://developer.adzuna.com/docs/search) for details.
- Results are filtered to Australia and the selected city. Adzuna's location matching is broad — you may see some listings from nearby areas.
- Skill counts in the heatmap reflect raw mention frequency in job descriptions. A job posting "Python preferred" and one requiring "5+ years Python" both count as one mention.
- Your API credentials are entered directly in the browser and sent only to the Adzuna API. This app has no backend and stores nothing.

---

## Built with

- [Adzuna API](https://developer.adzuna.com/) — job listing data
- [Claude](https://claude.ai) by [Anthropic](https://anthropic.com) — this tool was designed and built with Claude as an AI pair programmer
