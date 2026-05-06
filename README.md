# Replication Package

## Closing or Reproducing the Skills Gap? Python Integration in Finance Degrees and the University-Industry Interface

**Author:** Veliota Drakopoulou  
**Affiliations:** Higher Colleges of Technology; Embry-Riddle Aeronautical University  
**ORCID:** 0000-0002-1670-8033  
**Correspondence:** vdrakopoulou@yahoo.com  
**GitHub:** https://github.com/vdrakopoulou  
**Replication package DOI:** https://doi.org/10.5281/zenodo.18713524

## Overview

This replication package accompanies the manuscript *Closing or Reproducing the Skills Gap? Python Integration in Finance Degrees and the University-Industry Interface*. The study examines how Python is documented in finance-related degree curricula and compares these curriculum signals with an exploratory job-advert skill-signal dataset.

The curriculum dataset covers 140 finance-related programmes offered by 140 universities across 19 countries. Programmes were coded using a Depth-Scope-Authenticity rubric that captures whether Python is absent, mentioned superficially, confined to electives or pathways, or embedded as assessed finance-specific computational learning. The supplementary job-advert dataset contains 190 finance, FinTech, risk, data, and quantitative-role records, with 10 records per country, coded for Python and adjacent computational finance skill signals.

The package is intended to support reproducibility of the manuscript's descriptive statistics, indices, tables, figures, appendices, and supplementary job-advert alignment outputs. The job-advert component is exploratory and should be interpreted as an industry-facing skill signal rather than a representative estimate of all finance vacancies.

## Suggested Citation

Drakopoulou, V. (2026). *Replication package for Closing or Reproducing the Skills Gap? Python Integration in Finance Degrees and the University-Industry Interface* [Data set and code]. Zenodo. https://doi.org/10.5281/zenodo.18713524

## Repository Structure

```text
Replication_When Finance Speaks Python/
├── Appendices/
├── Code/
│   └── replication_analysis.py
├── Data/
│   ├── Python_in_Finance_Curriculum_scored.csv
│   ├── Python_in_Finance_Curriculum_scored.xlsx
│   └── JobAdvert/
│       └── job_ads_coded_for_table5.csv
├── Documentation/
│   ├── MANIFEST.md
│   └── checksums_sha256.txt
├── Figures/
├── Tables/
│   ├── Excel/
│   │   ├── job_advert_addon_summary_final.xlsx
│   │   └── table5_job_advert_curriculum_alignment.xlsx
│   └── manuscript and model-output CSV/TXT files
├── README.md
└── README_replication_package.md
```

## Data Files

### Curriculum Data

`Data/Python_in_Finance_Curriculum_scored.csv` is the primary programme-level dataset used to reproduce the curriculum analysis. The Excel version is provided as `Data/Python_in_Finance_Curriculum_scored.xlsx` for inspection.

Key fields include:

- `University_ID`: anonymized or structured programme identifier.
- `Country`: country or jurisdiction of the programme.
- `University_Name`: university name.
- `Program_Name`: programme title.
- `Degree_Level`: degree label or level recorded from documentation.
- `Academic_Year`: academic year of the coded documentation where available.
- `Evidence_Type`: type of evidence used, such as programme page, handbook, catalogue, or module descriptor.
- `Evidence_URL`: source URL where available.
- `Python_Found`: indicator of whether Python was explicitly documented.
- `Depth`: rubric score from 0 to 4 for vertical progression of Python use.
- `Scope`: rubric score from 0 to 4 for breadth of Python use across modules or learning contexts.
- `Authenticity`: rubric score from 0 to 4 for assessed, finance-specific, realistic Python use.
- `Python_Index`: summed score, calculated as `Depth + Scope + Authenticity`.
- `Python_Index_Normalised`: normalized index, calculated as `Python_Index / 12`.
- `graduate_program`: binary programme-level indicator used for exploratory regression.
- `Comments`: coder notes summarizing how Python is positioned in the curriculum.

### Supplementary Job-Advert Data

`Data/JobAdvert/job_ads_coded_for_table5.csv` contains the exploratory job-advert skill-signal records. The sample includes 190 role records, with 10 records per country. It is purposive and focused on Python-oriented or data-intensive finance, FinTech, analytics, risk, and quantitative roles.

Key fields include:

- `job_id`: job-record identifier.
- `platform`: job platform or source type.
- `country`: country associated with the advert.
- `job_title`: role title.
- `employer_name`: employer name where recorded.
- `employer_type`: employer classification.
- `role_family`: role grouping, such as finance, FinTech, data, risk, or quantitative role.
- `python_flag`, `sql_flag`, `r_flag`: binary indicators for programming-language signals.
- `ml_ai_flag`, `data_analytics_flag`: binary indicators for machine-learning, AI, or data-analytics signals.
- `risk_modeling_flag`, `portfolio_flag`, `algo_trading_flag`: binary indicators for finance-specific computational signals.
- `programming_required_flag`, `programming_preferred_flag`: binary indicators for whether programming is signalled as required or preferred.
- `ml_data_combined`: combined ML/data indicator.
- `finance_signal`: combined risk, portfolio, investment analytics, algorithmic trading, or quantitative trading indicator.
- `job_algorithmic_skill_index`: mean of eight binary skill indicators.
- `curriculum_index`: corresponding country-level curriculum Python index.
- `quality_flag`: internal quality or review indicator.

## Tables and Figures

The `Tables/` folder contains generated CSV and TXT outputs from the curriculum analysis, including country summaries, degree-level summaries, reliability/factor-structure outputs, regression outputs, mixed-model outputs, and robustness checks.

The `Tables/Excel/` folder contains the supplementary Excel tables requested for replication:

- `table5_job_advert_curriculum_alignment.xlsx`
- `job_advert_addon_summary_final.xlsx`

The `Figures/` folder contains generated PNG figures, including mean curriculum Python index by country and Depth-Scope-Authenticity profiles by country.

The package file names preserve the original generated output names. If the manuscript table numbering changes during revision, use file names and table titles rather than table numbers alone to identify outputs.

## Software Requirements

The quantitative replication script requires Python 3.9 or later and the following packages:

```text
pandas
numpy
scipy
statsmodels
matplotlib
openpyxl   # optional, useful for inspecting Excel files
```

A minimal installation command is:

```bash
pip install pandas numpy scipy statsmodels matplotlib openpyxl
```

## Reproducing the Outputs

After extracting the package, run the following commands from the package root:

```bash
cd "Replication_When Finance Speaks Python"
python Code/replication_analysis.py
```

The script reads:

```text
Data/Python_in_Finance_Curriculum_scored.csv
```

and writes reproducible outputs to:

```text
Tables/
Figures/
Appendices/
```

Running the script will overwrite the generated CSV, TXT, and PNG files in those folders. The supplementary job-advert Excel workbooks are included for inspection and alignment reporting; they are not regenerated by the main curriculum replication script.

## Checksums

SHA-256 checksums are provided in:

```text
Documentation/checksums_sha256.txt
```

To verify file integrity from the package root on macOS or Linux, run:

```bash
shasum -a 256 -c Documentation/checksums_sha256.txt
```

On systems using GNU coreutils, the equivalent command is:

```bash
sha256sum -c Documentation/checksums_sha256.txt
```

## Methodological Notes

The curriculum analysis is document-based. Public programme documents are treated as evidence of the represented or intended curriculum, not as direct observation of classroom practice. Programmes with no explicit reference to Python in the collected documents are coded as having no documented Python integration, even though Python may still be used informally by instructors.

The job-advert analysis is supplementary and exploratory. The records were selected to provide an employer-facing comparator for data-intensive finance work. They should not be interpreted as a representative labour-market census or as prevalence estimates for all finance vacancies.

## Ethics and Data Use

The study uses publicly available programme documentation and publicly visible job-advert information. No human participants were recruited, no individual-level student or staff data were collected, and no restricted institutional materials were accessed. The analysis is intended to identify aggregate curriculum and skill-signal patterns rather than to rank individual programmes or institutions.

## Contact

Questions about the replication package may be directed to:

Veliota Drakopoulou  
vdrakopoulou@yahoo.com  
ORCID: 0000-0002-1670-8033  
GitHub: https://github.com/vdrakopoulou
