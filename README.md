# Netflix Content Strategy Analysis
## Power BI Independent Project

## Project Overview
An independent Power BI analysis of Netflix's content 
library (8,800+ titles) to uncover platform strategy 
trends across content type, geography, and genre.

Built independently without tutorial guidance — 
dataset sourced from Kaggle (Shivam Bansal).

## Business Questions Answered
1. Has Netflix shifted focus from Movies to TV Shows 
   over time?
2. Which countries dominate Netflix content production?
3. How has content addition trend changed year over year?
4. What genres dominate the Netflix platform?

## Key Insights
- Netflix library is 68% Movies and 32% TV Shows — 
  Movies consistently dominate content volume
- USA produces 28% of all Netflix content — nearly 
  3x more than India in 2nd place
- Both Movies and TV Shows peaked in 2019 then declined 
  — reflecting COVID-19 global production impact
- International Movies is the #1 genre with 3,317 titles 
  — indicating Netflix's strong global audience focus
- Stand-Up Comedy surprisingly strong at #2 suggesting 
  Netflix invests heavily in comedy originals

## Dashboard Pages
- **Page 1** — Content Overview (Movies vs TV Shows 
  split, KPI cards, key insight)
- **Page 2** — Content by Country (Top 10 countries 
  by title count)
- **Page 3** — Content Addition Trends 2008-2021 
  (Movies vs TV Shows year over year)
- **Page 4** — Top Genres on Netflix (Top 10 genres 
  by title count)

## Data Cleaning Steps
- Removed duplicate rows and blank values
- Split country column by delimiter into rows 
  for accurate geographic analysis
- Split genre column by delimiter into rows 
  for accurate genre analysis
- Trimmed whitespace from all text columns
- Blank country values filled as "United States" 
  based on US representing 31% of content distribution

## Data Cleaning Assumptions
- ~500 rows with blank country values assigned 
  to "United States" based on overall distribution
- Dataset covers content available as of 2021 — 
  does not reflect current Netflix library

## DAX Measures Written
```dax
Total Shows = DISTINCTCOUNT(netflix[show_id])

Total Movies = 
CALCULATE(
    DISTINCTCOUNT(netflix[show_id]),
    netflix[type] = "Movie"
)

Total TV Shows = 
CALCULATE(
    DISTINCTCOUNT(netflix[show_id]),
    netflix[type] = "TV Show"
)
```

## Known Limitations
- Country and genre columns split on same table — 
  DISTINCTCOUNT used to handle duplicate show_ids
- Dataset is static — does not reflect Netflix 
  library changes after 2021
- No viewership or rating data available — 
  analysis limited to content volume metrics

## Tools Used
Power BI Desktop | Power Query | DAX | Kaggle Dataset

## Dataset Source
Netflix Movies and TV Shows — Shivam Bansal (Kaggle)

## Screenshots

### Content Overview
![Page 1](https://github.com/DeepakKhati/Netflix-Content-Strategy-Analysis/blob/main/Screenshot/01_overview.png)

### Content By Country
![Page 2](https://github.com/DeepakKhati/Netflix-Content-Strategy-Analysis/blob/main/Screenshot/02_Content.png)

### Content Addition Trends 2008-2021
![Page 3](https://github.com/DeepakKhati/Netflix-Content-Strategy-Analysis/blob/main/Screenshot/03_Trends.png)

### Top Genres On Netflix 
![Page 4](https://github.com/DeepakKhati/Netflix-Content-Strategy-Analysis/blob/main/Screenshot/04_genre.png)

