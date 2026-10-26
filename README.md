# Netflix Movies & TV Shows Analysis | Power BI Dashboard

An interactive Power BI report that explores Netflix's catalogue of movies and TV shows: how much content was released each year, how audiences rate it, and how runtimes and age certifications differ between formats.

![Executive Dashboard]
<img width="695" height="389" alt="executive_dashboard" src="https://github.com/user-attachments/assets/7fe96c46-eb5c-4379-a667-fef0aa931e52" />


![Viewers Insights]
<img width="691" height="389" alt="Viwers insights" src="https://github.com/user-attachments/assets/61ed395f-772d-4361-8c4d-1c52d9109484" />

![Average runtime over years]
<img width="691" height="386" alt="AverageRuntimeoveryears" src="https://github.com/user-attachments/assets/a18fa26d-2ae8-4f8e-9dcb-3318f133059e" />**

![Sum of IMDB votes over years]
<img width="692" height="387" alt="SumofIMDBVotesoveryears" src="https://github.com/user-attachments/assets/aa3c505a-feaa-46fd-9151-9d6769f777a1" />

---

## Project Overview

| | |
|---|---|
| **Tool** | Microsoft Power BI Desktop |
| **Data prep** | Power Query Editor |
| **Calculations** | DAX (measures and a calculated column) |
| **Data source** | CSV file (`Netflix.csv`) |
| **Dataset size** | 5,283 titles (3,407 movies, 1,876 TV shows) |
| **Release years covered** | 1953 – 2022 |

## Business Questions

1. How has Netflix's catalogue grown over the years?
2. Which titles attract the most audience votes?
3. How do IMDb scores vary by age certification?
4. How do runtimes differ between movies and TV shows, and how have they changed over time?

---

## Dataset

The data was imported into Power BI from a CSV file. Each row is one title.

| Column | Description |
|---|---|
| `id` | Unique Netflix title ID |
| `title` | Name of the movie or show |
| `type` | `MOVIE` or `SHOW` |
| `description` | Short synopsis |
| `release_year` | Year of release |
| `age_certification` | Age rating (e.g. TV-MA, TV-14, PG-13, R) |
| `runtime` | Duration in minutes (per episode for shows) |
| `imdb_id` | IMDb identifier |
| `imdb_score` | IMDb rating (out of 10) |
| `imdb_votes` | Number of IMDb votes |

---

## Data Cleaning (Power Query Editor)

Cleaning was done in Power Query Editor before loading the data into the model.

<!-- Edit this list so it matches exactly what you did in Power Query. -->
- Imported the CSV and promoted the first row to headers
- Set the correct data types (text, whole number, decimal)
- Removed duplicate rows
- Handled missing values in `age_certification`, `description` and `imdb_votes`
- Fixed garbled characters in text columns
- Removed unused columns (e.g. the `index` column)
- Renamed the table to `Netflix Movie & TV Series data`

## Data Model

| Table | Purpose |
|---|---|
| `Netflix Movie & TV Series data` | Main cleaned fact table |
| `Measure Table` | Holds the DAX measures |

**DAX measures**

| Measure | What it shows |
|---|---|
| `Average runtime Movies` | Average runtime (minutes) of movies |
| `Average Runtime Shows` | Average runtime (minutes) of TV shows |

**Calculated column:** `Rating Score` <!-- add a one-line description of how you calculated it -->

---

## Report Pages

| # | Page | Visual | What it shows |
|---|---|---|---|
| 1 | Data set home page | Column chart + line chart | Top titles by rating score and number of titles by release year |
| 2 | Clustered combo chart | Column + line combo | IMDb score and votes by release year |
| 3 | Area chart | Area chart | Total IMDb votes by release year |
| 4 | Stack Area/Line chart | Stacked area chart | Runtime trend by release year |
| 5 | Scatter plot | Scatter chart | IMDb score by age certification |
| 6 | Executive Dashboard | Combined view | Summary of the key trends on one page |
| 7 | Viewers insights | Combined view | Audience-focused view: ratings, votes and runtime |
| 8 | Key Insights | Text summary | Written takeaways for each page |

Every page has **slicers** for `type` and `release_year`, plus **KPI cards** for average movie runtime, average show runtime and title count. Navigation buttons link the dashboard pages.

---

## Key Insights

- **Catalogue is recent-heavy.** Releases peaked at 749 titles in 2019.
- **Hits drive engagement.** Inception, Forrest Gump and Breaking Bad lead in votes.
- **Growth after 2010.** Titles and votes rose sharply and peaked around 2017–2019. Votes peaked at 9.3M in 2017.
- **Best-rated content.** TV-14 (about 7.25) and TV-MA (about 7.07) score highest; movie certifications sit at about 6.2–6.5.
- **Runtime gap.** Movies average about 101 minutes; shows about 39 minutes.
- **Falling average runtime.** It trends down towards 75–100 minutes, probably because of more TV shows.
- **2022 dip.** Likely incomplete data, not a real decline.

---

## How to Use

1. Download "Netflix_Project.pbix using: https://1drv.ms/u/c/b578293997cbefbf/IQBjReqds1noQKmLb1IOIquwAaYfwkKS33ammfKaA5FFScc?e=I0nPOh".
2. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
3. Use the `type` and `release_year` slicers to filter, and the navigation buttons to move between pages.

> If Power BI asks for the data source path, go to **Home → Transform data → Data source settings** and point it to your local copy of 'Netflix CSV' https://1drv.ms/x/c/b578293997cbefbf/IQAsb4UYuVOzSLH_9d61v7JVAWIqNyddMy1OuhnGvl8-IOs?e=hjRnRM`.

## Repository Structure

```
├── Netflix_Project.pbix     # Power BI report
├── Netflix.csv              # Source data
├── images/                  # Dashboard screenshots
└── README.md
```

## Skills Demonstrated

Data cleaning with Power Query · Data modelling · DAX measures · Dashboard design · Data storytelling

## Author

**Manish Giri**
<!-- Add your LinkedIn / email link here -->
