### [Download ZIP file containing all Global Capitalism Index data](https://github.com/DemocracyandCapitalismLab/GlobalCapitalismIndex/archive/refs/heads/main.zip)

# Global Capitalism Index — Data Downloads

The Global Capitalism Index (GCI) measures the institutional conditions that
support market systems. It covers **170 countries** from **2009 to 2025**, and is
built from **213 underlying datasets** organised into **33 domains** and **eight
subindices**. Every score carries a 95% bootstrap confidence interval.

The index is produced by the Democracy and Capitalism Lab at the Karsh Institute
of Democracy, University of Virginia, in partnership with the Institute for
Business and Society at the Darden School of Business. Interactive exploration,
country profiles, and background are at
**[capitalismindex.com](https://capitalismindex.com)**. This repository is the
download point for the underlying data.

The data is released under [CC BY-NC 4.0](LICENSE). It is free to use, share, and
build on for research, teaching, journalism, and analysis. **Commercial
use requires prior written permission** from the Democracy and Capitalism Lab.

Anyone is welcome to use this data. We ask that you attribute our work by citing the accompanying
academic paper and the Global Capitalism Index website at **[capitalismindex.com](https://capitalismindex.com)**
The the [Citation](#citation) section below lists each citation. 

## Data files

All data is in the [`data/`](data) folder as `.csv` files: one for the composite
index and one for each of the eight subindices.

| File | Contents | Rows |
|---|---|---:|
| [`gci_composite.csv`](data/gci_composite.csv) | Composite GCI score | 2,809 |
| [`gci_property_rights.csv`](data/gci_property_rights.csv) | Strength of Property Rights and Private Ownership | 2,970 |
| [`gci_market_supporting_policy.csv`](data/gci_market_supporting_policy.csv) | Market-Supporting Policy | 2,763 |
| [`gci_labor_market_openness.csv`](data/gci_labor_market_openness.csv) | Labor Market Openness | 2,409 |
| [`gci_market_competition.csv`](data/gci_market_competition.csv) | Market Competition | 2,884 |
| [`gci_capital_market_sophistication.csv`](data/gci_capital_market_sophistication.csv) | Capital Market Sophistication | 2,826 |
| [`gci_banking_system.csv`](data/gci_banking_system.csv) | Depth and Stability of the Banking System | 2,797 |
| [`gci_new_business_formation.csv`](data/gci_new_business_formation.csv) | New Business Formation and Growth | 2,700 |
| [`gci_free_flow_goods_capital.csv`](data/gci_free_flow_goods_capital.csv) | Free Flow of Goods and Capital | 2,717 |

All files are UTF-8 with LF line endings. Missing values are empty fields, not
zeros, as several subindices have legitimate scores at or near 0.00.

## Reference documents

### Data Dictionary

Column definitions for every file, and guidance on reading the coverage fields.

[View on GitHub](docs/gci_data_dictionary.md)

### Codebook

Dataset-level documentation for all 213 inputs: source links, native scales,
transformations, and reliability grades.

[View on GitHub](docs/gci_codebook.md) · [Download as PDF](docs/gci_codebook.pdf)

### Academic Paper with Compositional Methodology

The academic paper provides a detailed overview of the theoretical framework and compositional methodology.

[Download as PDF](docs/gci_whitepaper.pdf)

### Peer reviews

Each of the eight subindices was reviewed by external scholars with subject
expertise in that domain. Reviewers were asked to assess the theoretical
justification for the subindex, the appropriateness of its domain structure,
and the merit of each dataset selected as an input. Ten reviewers took part,
covering all eight subindices. Where a review
prompted a change to the index, that change is reflected in the current data
and described in the academic paper. The instructions provided to reviewers are
also in the academic paper.

[Browse the reviews](docs/peer_review)

## Coverage

The composite is scored for 170 countries. Individual subindices cover up to
175, because five countries (Cuba, Eritrea, Palestine, Somalia, and South Sudan) 
appear in one or more subindices but never meet the 5 of 8 threshold
required for a composite score. They therefore appear in subindex files and never
in `gci_composite.csv`. Annual coverage varies with data availability.

| Subindex | Countries in panel | Scored in 2025 |
|---|---:|---:|
| Property Rights | 175 | 175 |
| Market Competition | 175 | 159 |
| Market-Supporting Policy | 172 | 158 |
| Free Flow of Goods and Capital | 172 | 145 |
| Capital Market Sophistication | 171 | 161 |
| Banking System | 171 | 166 |
| New Business Formation | 163 | 153 |
| Labor Market Openness | 153 | 123 |
| **Composite** | **170** | **161** |

## Notes on Use

**Scores are year-relative:** Normalization is computed year by year, which
preserves cross-national variation but means a country's score can move because
the surrounding distribution shifted rather than because its own institutions
changed. For claims about relative position over time, ranks are the safer
instrument.

**Confidence intervals:** Countries whose intervals overlap
substantially cannot be reliably ranked on point estimates alone. The intervals
propagate resampling and imputation variance, but not uncertainty in period
boundaries, component counts, reliability scores, or source measurement error.

## Peer Review

Each of the eight subindices was reviewed by external scholars with subject
expertise in that domain. Reviewers were asked to assess the theoretical
justification for the subindex, the appropriateness of its domain structure,
and the merit of each dataset selected as an input. Ten reviewers took part,
covering all eight subindices.

Reviews are posted in full in [`docs/peer_review/`](docs/peer_review), with a
table listing each reviewer and the subindex they assessed. 

## Citation

Please cite the Global Capitalism Index:

> Roberts, Thomas Villalobos, Zachary Esses Johnson, Scott C. Miller, Hannah
> Knox Tucker, Michael J. Lenox, Sidney M. Milkis, Katharine Shadlock, Meghana
> Annamaneni, Eliza Bentley, Grace Higgins, Arya Kumar, Sebastian Nabatoff. 2026.
> "Global Capitalism Index [Country-Year] Dataset 2025," Democracy and Capitalism
> Lab, Karsh Institute of Democracy and Institute for Business and Society,
> Darden School of Business, University of Virginia.

And the accompanying academic paper:

> Roberts, Thomas Villalobos, Zachary Esses Johnson, Scott C. Miller, Hannah
> Knox Tucker, Michael J. Lenox, Sidney M. Milkis, Katharine Shadlock. 2026. "The
> Global Capitalism Index: A Multidimensional Index for Measuring Market
> Systems," Democracy and Capitalism Lab, Karsh Institute of Democracy and
> Institute for Business and Society, Darden School of Business, University of
> Virginia.

For the details outlined in the GCI codebook:

> Roberts, Thomas Villalobos, Zachary Esses Johnson, Scott C. Miller, Hannah Knox
> Tucker. 2026. "Global Capitalism Index Codebook," Democracy and Capitalism Lab,
> Karsh Institute of Democracy and Institute for Business and Society, Darden
> School of Business, University of Virginia.

## Questions and corrections

Documentation errors, dataset issues, and methodological questions can directed to the authors listed in the academic paper.
Researchers using the GCI in published work are encouraged to notify the team so we can maintain an accurate
record of applications. The GCI is updated annually as new data become available.
