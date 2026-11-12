# Predicting Life Expectancy with Linear Regression

Final project for STAT 4210 Regression Analysis (Kennesaw State University), December 2024.
Author: Nakai Zemer.

**Question:** which country-level factors are associated with life expectancy at birth, and how well can a multiple linear regression model predict it?

**Data:** World Health Organization (WHO) 2021 country-level data: life expectancy at birth plus six candidate predictors (homicide rate, unintentional poisoning mortality, suicide mortality, road traffic mortality, universal health coverage index, domestic general government health expenditure). Life expectancy is reported for 185 countries. After listwise deletion the first two models use 175 and 179 countries; the final model uses 171 after influential outliers are removed.

## Headline results

Final model (171 countries): adjusted R-squared 0.838, residual standard error 2.88 years, F = 177.1 on 5 and 165 df.

| Predictor | Estimate | p-value |
|---|---|---|
| Suicide mortality rate | -0.157 | 0.0002 |
| Unintentional poisoning mortality rate | -1.699 | < 0.0001 |
| Homicide rate | -0.100 | < 0.0001 |
| Road traffic mortality rate | -0.106 | 0.007 |
| Universal health coverage index | 0.317 | < 0.0001 |

These are associations in observational, cross-sectional data, not causal effects. See the report for the three models compared, assumption checks and limitations.

## Files

- `life_expectancy_final_report.pdf` / `.qmd` - the final report (R, Quarto).
- `life_expectancy_project_proposal.pdf` / `.qmd`, `references.bib` - the project proposal.
- `who_life_expectancy_model_presentation.qmd`, `life_expectancy_final_report_html.qmd` - presentation and HTML versions of the report (sources only; see the note on the WHO logo below).
- `who_life_expectancy_model.qmd` - pulls indicators from the WHO Global Health Observatory API with the `ghost` package.
- `who_life_expectancy.qmd` - exploratory work on the WHO data.
- `datasets/who_life_expectancy.csv`, `datasets/who_life_expectancy_indicators.csv` - the two WHO files the report reads.

## Data source and attribution

Data: World Health Organization, [Global Health Observatory](https://www.who.int/data/gho) and [World Health Statistics](https://www.who.int/data/gho/data/themes/world-health-statistics). WHO data is released under the [CC BY-NC-SA 3.0 IGO](https://creativecommons.org/licenses/by-nc-sa/3.0/igo) licence (noncommercial use, attribution, share-alike).

This project is not endorsed by or affiliated with WHO. The WHO emblem/logo is deliberately not included in this repository, because WHO requires written permission to use it. The two `.qmd` files that build the HTML report and the presentation reference a `WHO_on_white.png` logo image; remove that line (or supply your own image) to render them.

The 296 MB extract produced by `who_life_expectancy_model.qmd` is not included.

## Writeup on the web

https://kai.do/projects/life-expectancy-regression/
