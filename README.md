# Jawwy TV Data Analysis

Jawwy TV data analysis project covering viewer behavior, recommendation modeling, and viewership forecasting — completed as part of the **stc Data Analyst Virtual Experience**, in partnership with the **Misk Foundation**.

Working with **1M+ viewing records** from the Jawwy TV platform, this project uncovers engagement patterns and delivers three data products: a behavioral analysis, a demand forecasting model, and a content recommendation engine.

---

## Project Overview

| | |
|---|---|
| **Program** | stc Data Analyst Virtual Experience × Misk Foundation |
| **Domain** | OTT / Streaming viewer analytics |
| **Records analyzed** | 1,048,575 viewing events |
| **Tools** | Python, pandas, statsmodels, scikit-learn, Plotly, Matplotlib |
| **Deliverables** | 3 Jupyter notebooks + 1 executive presentation |

---

## Tasks

The project is split into four tasks, each addressing a distinct analytical objective.

### Task 1 — Interaction Data & Playback Quality

**Notebook:** [`stc_TV_Task1.ipynb`](notebooks/stc_TV_Task1.ipynb)

Analyzes viewing behavior across movies vs. series and playback quality (HD/SD), using 1,048,575 records with 13 fields including duration, HD flag, and genre.

- Most-watched titles and genres by total watch time
- Movies vs. Series engagement comparison
- HD vs. SD playback share by program type

### Task 2 — Demand Forecasting

**Notebook:** [`stc_TV_Task2.ipynb`](notebooks/stc_TV_Task2.ipynb)

Builds a time-series forecasting model on 86 days of daily watch-hour totals (Jan–Apr 2018) to predict demand two months ahead.

- Seasonal decomposition (trend / seasonality / residual)
- Grid search across 64 SARIMA parameter combinations, selected by AIC
- 60-day forecast with confidence intervals

### Task 3 — Recommendation Engine

**Notebook:** [`stc_TV_Task3.ipynb`](notebooks/stc_TV_Task3.ipynb)

Builds a collaborative-filtering recommender using user ratings across 8,013 titles and 11,578 active users.

- User × item rating matrix (pivot table)
- K-Nearest Neighbors with cosine similarity
- Top-5 title recommendations for any given program

### Task 4 — Data Storytelling & Recommendations

**Deliverable:** [`Jawwy_TV_Data_Story.pptx`](presentation/Jawwy_TV_Data_Story.pptx)

Translates the findings from Tasks 1–3 into a data story for a non-technical audience, with actionable recommendations for the product team.

---

## Key Findings

| Finding | Detail |
|---|---|
| **Declining engagement** | Daily watch hours fell from **883 hrs/day** (Jan avg) to **696 hrs/day** (Apr avg) — a **21% decline** over 4 months |
| **Series outperform movies per user** | Series viewers watch **7.2×** more per user than movie viewers (65.4 hrs vs. 9.1 hrs), despite a smaller audience (3,901 vs. 11,355 users) |
| **Animation dominates content** | Animation accounts for **38%** of all viewing records; *The Boss Baby* and *Moana* top the most-watched list |
| **Playback quality gap** | Series lean far more toward standard definition (56% SD) than movies (36% SD) — likely a bandwidth-saving pattern in long viewing sessions |
| **Forecast model** | Best model: `SARIMA(0,1,1)×(0,1,1,12)`, AIC = 909.6, forecasting a continued downward trend over the next 60 days |
| **Recommendation quality** | KNN-based recommendations for *Moana* returned genre-consistent titles (*Trolls*, *Surf's Up: WaveMania*, *The Mermaid Princess*, *The Boss Baby*, *The Jetsons & WWE: Robo-WrestleMania!*) |

---

## Recommendations

1. **Deploy the Recommendation Engine** — launch the validated model as a "Recommended for You" row on the home screen.
2. **Operationalize the Forecast Model** — feed SARIMA output into infrastructure and content-release planning.
3. **Expand Family & Animation Placement** — animation accounts for 38% of viewing; allocate a dedicated home-screen section.
4. **Investigate the HD Quality Gap in Series** — determine the underlying cause of the higher SD playback rate in series content.
5. **Prioritize Series in New Content Investment** — series generate 7.2× the per-user watch time of movies.

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-data%20wrangling-150458?logo=pandas&logoColor=white)
![statsmodels](https://img.shields.io/badge/statsmodels-SARIMA-orange)
![scikit-learn](https://img.shields.io/badge/scikit--learn-KNN-F7931E?logo=scikit-learn&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-interactive%20viz-3F4F75?logo=plotly&logoColor=white)

| Library | Purpose |
|---|---|
| `pandas`, `numpy` | Data wrangling and numerical computation |
| `pyxlsb` | Reading `.xlsb` Excel files |
| `plotly`, `matplotlib` | Interactive and static visualizations |
| `statsmodels` | SARIMA time-series forecasting |
| `scikit-learn`, `scipy` | K-Nearest Neighbors recommendation model |

---

## Repository Structure

```text
Jawwy-TV-Data-Analysis/
│
├── notebooks/
│   ├── stc_TV_Task1.ipynb        # Viewing behavior & HD/SD analysis
│   ├── stc_TV_Task2.ipynb        # Demand forecasting model
│   └── stc_TV_Task3.ipynb        # Content recommendation engine
│
├── presentation/
│   └── Jawwy_TV_Data_Story.pptx  # Executive summary & recommendations
│
└── README.md
