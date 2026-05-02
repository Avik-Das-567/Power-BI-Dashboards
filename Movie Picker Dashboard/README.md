# Christmas Movie Picker | Power BI Dashboard
## Overview

**Christmas Movie Picker** is an interactive **Power BI dashboard** designed to help users discover Christmas-themed movies based on their preferences. The project walks through the complete Power BI workflow - from importing raw data to cleaning, modeling, visualization, and interactivity - using a real-world movie dataset. The dashboard enables users to filter movies by **genre**, **rating**, **IMDb rating range**, **runtime**, and **popularity (votes)**, making it easy to find a suitable movie for the holiday season.

---

## Project Goals
I built this project to:
- Utilize **core Power BI skills** in an end-to-end scenario
- Perform **data cleaning** and **transformation** using Power Query
- Build an **interactive dashboard** with slicers and visuals
- Apply **analytical decision-making**, such as choosing the right popularity metric
- Design a clean, user-friendly report layout

---

## Dataset Description

Link: https://www.kaggle.com/datasets/jonbown/christmas-movies

The dataset `christmas_movies.csv` is a collection of **Christmas-related movies from IMDb**.

Key Columns Used:
- `Title` – Movie name
- `Rating` – Movie / TV certification
- `Runtime` – Duration in minutes
- `IMDb Rating` – Average IMDb score
- `Genre` – One or more genres (comma-separated)
- `Released` – Release year
- `Director` – Movie director
- `Stars` – Lead actors
- `Votes` – Number of IMDb votes

During initial exploration, several data quality issues were identified, such as inconsistent ratings, blank values, and multiple genres stored in a single column.

---

## Data Preparation & Cleaning (Power Query)
All data transformation steps were performed using **Power Query Editor**.
### Genre Normalization:
- The `Genre` column often contained multiple values separated by commas
- The column was split into: `Genre.1`, `Genre.2`, etc.
- `Genre.1` was selected as the **primary genre** and used in visuals and slicers

This approach simplified filtering while retaining meaningful genre information.

### Rating Consolidation:

The original dataset included many inconsistent or outdated ratings, such as:
- `TV-14`, `TV-G`, `TV-PG`, `TV-MA`
- `Approved`, `Passed`, `Not Rated`, and blanks

These were standardized into common movie ratings:

| Original Rating              | Standardized Rating |
| ---------------------------- | ------------------- |
| TV-14                        | PG-13               |
| TV-G                         | G                   |
| TV-PG                        | PG                  |
| TV-MA                        | R                   |
| Approved / Not Rated / Blank | Unrated             |

This cleanup ensures consistent filtering and better user experience.

### Popularity Metric Selection:

Although **IMDb Rating** is included, the **Votes** column was chosen as the primary indicator of popularity.

Votes provide a stronger signal of audience engagement and are used to rank movies in the dashboard.

---

## Dashboard Components
### Movies Table:
A central table displays detailed information for each movie:

**Title, Primary Genre, Director, Release Year, Votes, Lead Actors**

Formatting choices:
- Column headers cleaned and renamed
- `Release Year` and `Votes set` to **"Don't summarize"**
- Table dynamically updates based on all slicer selections

### Top 5 Movies by Votes:
A **clustered column chart** shows the **Top 5 most popular movies** based on vote count:
- **X-axis:** Movie Title
- **Y-axis:** Votes
- Green bars with data labels for clarity

The chart automatically recalculates when filters are applied, helping users quickly identify popular options.


### Interactive Filters (Slicers):
Four slicers allow users to personalize their movie search:
- **Genre**
  - Dropdown slicer using the primary genre
- **Rating**
  - Dropdown slicer with standardized ratings:
    - G, PG, PG-13, R, Unrated
- **IMDb Rating (Range)**
  - Slider to define minimum and maximum IMDb rating
- **Runtime (Minutes)**
  - Slider to filter movies by duration

All slicers are consistently styled and interact with every visual on the report.

---

## Dashboard Interactivity
Users can:
- Adjust slicers to define preferences
- Instantly see the filtered movie list
- Identify the most popular movies within their criteria

This demonstrates how Power BI supports **exploratory analysis** and **decision-making** through interactive visuals.

---

## Key Learnings
This project helped reinforce:
- Data cleaning and transformation techniques
- Handling inconsistent categorical data
- Designing intuitive, interactive dashboards
- Choosing meaningful metrics for analysis
- Structuring beginner-friendly Power BI projects

---

## Conclusion

The **Christmas Movie Picker** project demonstrates how Power BI can be used beyond business reporting - applying analytics to entertainment and everyday choices. It showcases data preparation, visualization, and interactive dashboard design.

---
