# GCI Data Dictionary

Column definitions for every file in the Global Capitalism Index data release.
Dataset-level documentation of the 213 underlying inputs — sources, native
scales, transformations, and reliability grades — is in the
[Codebook](gci_codebook.md).

## `gci_composite.csv`

| Column | Type | Description |
|---|---|---|
| `country` | text | Country name |
| `iso` | text | ISO 3166-1 alpha-3 code. Join key |
| `year` | integer | Observation year, 2009–2025 |
| `n_obs` | integer | Number of the eight subindices observed for this country-year (5–8) |
| `gci_composite` | numeric | Composite GCI score, 0–100 |
| `gci_composite_lower` | numeric | Lower bound of the 95% bootstrap confidence interval |
| `gci_composite_upper` | numeric | Upper bound of the 95% bootstrap confidence interval |
| `ci_width` | numeric | Interval width. Equal to `gci_composite_upper` − `gci_composite_lower`; provided for convenience |

Subindex scores are not repeated in this file. Join the subindex files on `iso`
and `year` to assemble a wide panel.

## Subindex files

All eight share the same seven-column layout.

| Column | Type | Description |
|---|---|---|
| `country` | text | Country name |
| `iso` | text | ISO 3166-1 alpha-3 code. Join key |
| `year` | integer | Observation year, 2009–2025 |
| `n_obs_vars` | integer | Number of the subindex's underlying datasets observed for this country-year |
| *score* | numeric | Subindex score, 0–100. Column name varies by file |
| `index_lower_scaled` | numeric | Lower bound of the 95% bootstrap confidence interval |
| `index_upper_scaled` | numeric | Upper bound of the 95% bootstrap confidence interval |

Score column names, and the range of `n_obs_vars` in each file:

| File | Score column | `n_obs_vars` range | Datasets in subindex |
|---|---|---|---:|
| `gci_property_rights.csv` | `property_rights_scaled` | 9–31 | 31 |
| `gci_market_supporting_policy.csv` | `market_supporting_policy_scaled` | 4–20 | 20 |
| `gci_labor_market_openness.csv` | `labor_openness_scaled` | 4–12 | 13 |
| `gci_market_competition.csv` | `market_competition_scaled` | 6–31 | 31 |
| `gci_capital_market_sophistication.csv` | `cms_scaled` | 4–25 | 29 |
| `gci_banking_system.csv` | `banking_scaled` | 4–21 | 22 |
| `gci_new_business_formation.csv` | `business_growth_scaled` | 8–52 | 56 |
| `gci_free_flow_goods_capital.csv` | `free_flow_scaled` | 4–10 | 11 |

## Reading `n_obs` and `n_obs_vars`

Both columns count observed inputs, at different levels of the index hierarchy.

**`n_obs`** in the composite file counts how many of the eight subindices were
available for that country-year. A country-year is scored on the composite only
if at least five of eight are observed, so `n_obs` never falls below 5. Values
below 8 mean the composite rests on a subset of the eight pillars, and those
observations carry wider confidence intervals.

**`n_obs_vars`** in a subindex file counts how many of that subindex's underlying
datasets were observed for that country-year. The maximum never reaches the full
dataset count in the rightmost column above, because no country-year has every
dataset present: sources enter and exit the panel across 2009–2025, and the
adaptive PCA estimates within temporal periods using only the variables available
in each. Low values indicate a score built on thin information and should be read
alongside the confidence interval.

Neither column is a quality score. Use it as a coverage flag — for instance,
dropping observations below a threshold as a robustness check, or weighting by
interval width.

## Missing values

Missing values are empty fields. They are **not** zeros: several subindices have
legitimate scores at or near 0.00, so treating blanks as zeros will corrupt any
analysis. Both pandas and R read empty CSV fields as `NA` by default.
