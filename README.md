# Jawwy TV Viewership Data Analysis

A million viewing records reveal how users engage and where the platform can grow.

Completed as part of the **stc Data Analyst Virtual Experience** in partnership with the **Misk Foundation**.

The project analyzes **1,048,575 viewing events** and delivers three analytical solutions covering viewer behavior, demand forecasting, and content recommendations.

---

## Project Overview

| | |
|---|---|
| **Program** | stc Data Analyst Virtual Experience × Misk Foundation |
| **Domain** | OTT / Streaming Analytics |
| **Viewing Events** | 1,048,575 |
| **Tools** | Python, pandas, statsmodels, scikit-learn, Plotly, Matplotlib |
| **Deliverables** | 3 Jupyter notebooks + 1 executive presentation |

---

## Project Tasks

### Task 1 — Viewer Behavior & Playback Quality

**Notebook:** [`stc_TV_Task1.ipynb`](notebooks/stc_TV_Task1.ipynb)

Analyzes viewer behavior and playback quality across movies and series.

Key analysis includes:

- Most-watched titles and genres by total watch time
- Movies vs. series engagement
- HD vs. SD playback distribution
- Viewer and content-level engagement patterns

---

### Task 2 — Demand Forecasting

**Notebook:** [`stc_TV_Task2.ipynb`](notebooks/stc_TV_Task2.ipynb)

Builds a SARIMA time-series forecasting model using daily watch-hour data to estimate future viewing demand.

Key analysis includes:

- Trend and seasonal decomposition
- Grid search across 64 SARIMA parameter combinations
- Model selection using AIC
- 60-day demand forecast with confidence intervals

**Selected model:**

`SARIMA(0,1,1) × (0,1,1,12)`

---

### Task 3 — Recommendation Engine

**Notebook:** [`stc_TV_Task3.ipynb`](notebooks/stc_TV_Task3.ipynb)

Develops a collaborative-filtering recommendation engine using user ratings.

Key components include:

- User × item rating matrix
- K-Nearest Neighbors
- Cosine similarity
- Top-5 content recommendations

The model was tested using **8,013 titles** and **11,578 active users**.

---

### Task 4 — Data Storytelling & Recommendations

**Presentation:** [`Jawwy_TV_Data_Story.pdf`](presentation/Jawwy_TV_Data_Story.pdf)

Translates the analytical findings from Tasks 1–3 into an executive-level data story, highlighting key insights and actionable recommendations.

---

## Key Findings

| **Finding** | **Result** |
|---|---|
| **Declining engagement** | Daily watch hours decreased from **883 hrs/day** in January to **696 hrs/day** in April, approximately a **21% decline**. |
| **Series engagement** | Series viewers generated **7.2×** more watch time per user than movie viewers, at 65.4 hrs vs. 9.1 hrs. |
| **Animation dominance** | Animation represented **38%** of all viewing records, with *The Boss Baby* and *Moana* among the most-watched titles. |
| **Playback quality gap** | Series viewing had a higher SD share (**56%**) compared with movies (**36%**). |
| **Forecasting** | The selected SARIMA model was `SARIMA(0,1,1) × (0,1,1,12)`, with an AIC of **909.6**. |
| **Recommendations** | KNN-based recommendations for *Moana* produced genre-consistent titles including *Trolls*, *Surf's Up: WaveMania*, and *The Boss Baby*. |

---

## Recommendations

1. **Deploy the Recommendation Engine**  
   Integrate personalized recommendations into the platform experience to improve content discovery.

2. **Operationalize Demand Forecasting**  
   Use forecasted viewing demand to support infrastructure and content planning.

3. **Expand Family & Animation Placement**  
   Given the strong share of animation viewing, consider dedicated placement for family and animation content.

4. **Investigate the Series SD Gap**  
   Further investigate the higher SD playback share among series viewers to understand whether it is driven by user behavior, network conditions, or content availability.

5. **Prioritize Series Engagement**  
   The significantly higher per-user watch time for series suggests an opportunity to strengthen series-focused content and engagement strategies.

---

## Tech Stack

| **Library** | **Purpose** |
|---|---|
| `pandas`, `numpy` | Data wrangling and numerical computation |
| `pyxlsb` | Reading `.xlsb` datasets |
| `plotly`, `matplotlib` | Data visualization |
| `statsmodels` | SARIMA time-series forecasting |
| `scikit-learn`, `scipy` | KNN recommendation modeling and similarity analysis |

---

## Repository Structure

```text
Jawwy-TV-Data-Analysis/
│
├── notebooks/
│   ├── stc_TV_Task1.ipynb
│   ├── stc_TV_Task2.ipynb
│   └── stc_TV_Task3.ipynb
│
├── presentation/
│   └── Jawwy_TV_Data_Story.pdf
│
└── README.md
