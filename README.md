# InsightForge V1.0 — Final consolidated release

This version embeds the CSS directly inside `index.html`, so the styling works even if
the browser cannot resolve `styles.css`. `styles.css` is also included separately.

## Run
1. Extract the ZIP.
2. Open the extracted folder.
3. Open `index.html`, OR preferably run:
   `python -m http.server 8000`
4. Visit `http://localhost:8000`

## Files
- index.html — app + embedded CSS
- styles.css — same CSS as a separate file
- app.js — dashboard logic
- food_ordering_behavior_dataset.csv — demo dataset

## Upload
CSV is supported in this version.


V2.2 fixes the CSV filename extension check that could reject valid `.csv` files. The upload accepts `.csv` case-insensitively.

V2.3 improves CSV parsing: UTF-8 BOM removal, comma/semicolon/tab/pipe delimiter detection, quoted values, escaped quotes, and mixed newline handling.


## V2.4 improvements
- Adds dedicated skill-demand analysis for questions about skills.
- Splits multi-value skill cells using pipe, semicolon, comma, or newline delimiters.
- Counts each skill once per job posting and shows overall frequency.
- Adds a job-category × skill frequency table when a job category column is available.
- Avoids duplicate average KPI cards and duplicate chart titles.


## V2.5 improvements
- Makes KPI selection question-aware; skill questions show distinct skills and total skill mentions.
- Improves matching of plural and common aliases for job title, job category, salary, demand, experience, and remote-work columns.
- Adds a dedicated two-dimension combination analysis path to avoid redundant single-dimension charts.
- Produces clearer business-language insights for grouped comparisons.
- Preserves V2.4 individual skill counting and category-wise skill breakdown.


## V2.5.1 fixes
- Fixes KPI cards rendering as comma-separated text by returning valid card markup.
- Recognizes plural wording such as "job titles and job categories" as a two-dimension comparison.
- Routes combination questions to a single average-measure combination chart and avoids redundant single-dimension charts.


## V1.0 final release improvements
- Fixes KPI card markup in the dedicated skill-demand analysis.
- Shows quality/rating charts only when the business question asks about quality, ratings, satisfaction, or reviews, preventing unrelated charts in salary and demand analyses.
- Keeps full chart category labels visible with wrapping instead of truncating long job titles.
- Consolidates the tested V2.5.1 behavior and final UI/analysis fixes into one release.

## How the dashboard works
InsightForge uses automated, rule-based question and column matching with dataset profiling and aggregation logic to generate charts and insights. It does not currently call an external large language model API. Be accurate about this when describing the project.
