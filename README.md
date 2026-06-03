# Closing or Reproducing the Skills Gap?

## Python Integration in Finance Degrees and the University-Industry Interface

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18713524.svg)](https://doi.org/10.5281/zenodo.18713524)

**Author:** Veliota Drakopoulou  
**Affiliations:** Higher Colleges of Technology; Embry-Riddle Aeronautical University  
**ORCID:** https://orcid.org/0000-0002-1670-8033  
**Correspondence:** vdrakopoulou@yahoo.com  
**GitHub:** https://github.com/vdrakopoulou  
**Zenodo Replication package DOI:** https://doi.org/10.5281/zenodo.18713524

---

## What this package is about

Finance increasingly speaks through data, code, and algorithmic models. This replication package asks a simple but consequential question: are finance degrees helping students learn that language, or are they reproducing the skills gap by making computational learning optional, uneven, or invisible?

The package accompanies the manuscript **"When Finance Speaks Python: Mapping Python Integration in Finance Degrees and the University–Industry Skills Gap ."** It contains the data, code, tables, figures, and documentation needed to reproduce the study's analysis of Python integration in finance-related university programmes and its comparison with exploratory job-advert skill signals.

The study treats Python as more than a programming language. In this project, Python is used as a marker of **algorithmic curriculum capacity**: whether finance students are formally exposed to coding, data analytics, modelling, and authentic finance-specific computational work.

---

## At a glance

| Element | What is included |
|---|---|
| Curriculum sample | 140 finance-related programmes from 140 universities |
| Country coverage | 19 countries and jurisdictions |
| Core measure | Depth-Scope-Authenticity rubric, scored 0 to 4 on each dimension |
| Main index | Normalized Python Curriculum Index, scaled from 0 to 1 |
| Job-advert add-on | 190 finance, FinTech, data, risk, and quantitative-role records |
| Main purpose | Reproduce descriptive statistics, indices, tables, figures, and supplementary alignment outputs |
| Main caution | The curriculum data measure documented or represented curriculum, not classroom observation |

---

## What you can reproduce

This package allows readers to reproduce the main empirical backbone of the manuscript:

1. Descriptive statistics for Depth, Scope, Authenticity, the raw Python index, and the normalized Python index.
2. Country-level and degree-level summaries of documented Python adoption.
3. Reliability and factor-structure checks for the Python Curriculum Index.
4. Exploratory regression and mixed-model outputs.
5. Figures showing cross-national variation and Depth-Scope-Authenticity profiles.
6. Supplementary Excel tables for the job-advert and curriculum-alignment analysis.

The package is designed for three audiences: reviewers checking reproducibility, researchers adapting the rubric, and curriculum teams interested in mapping computational finance provision.

---

## How the study works

The curriculum analysis uses public programme documents such as programme pages, handbooks, course catalogues, regulations, and module descriptors. Each programme is coded using a three-part rubric:

| Dimension | What it captures | Low score means | High score means |
|---|---|---|---|
| Depth | Vertical development of Python across the programme | No Python or only isolated exposure | Python is developed from introductory to advanced levels |
| Scope | Breadth of Python use across modules and learning contexts | One module, workshop, or narrow activity | Python appears across multiple finance subfields |
| Authenticity | Realism and assessment of Python use | Demonstrations, toy examples, or no assessed coding | Real data, finance-specific projects, capstones, or industry-facing work |

The normalized index is calculated as:

```text
Python_Index_Normalised = (Depth + Scope + Authenticity) / 12
```

The supplementary job-advert analysis then compares these curriculum signals with a purposive sample of employer-facing skill signals from finance, FinTech, data, risk, and quantitative-role adverts. The job-advert data are exploratory. They are useful for triangulation, but they are not a census of all finance vacancies.

---

## Repository structure

```text
Replication_When Finance Speaks Python/
├── Appendices/
│   ├── appendix_A1_sample_by_country.csv
│   ├── appendix_A2_sample_by_degree_level.csv
│   ├── appendix_B1_rubric_definitions.csv
│   ├── appendix_B2_rubric_examples.csv
│   ├── appendix_C1_descriptives_key_variables.csv
│   ├── appendix_C2_correlation_matrix.csv
│   ├── appendix_D1_full_ols_regression.csv
│   └── appendix_D2_mixed_effects_parameters.csv
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
│   ├── figure2_mean_index_by_country.png
│   └── figure3_depth_scope_authenticity_by_country.png
├── Tables/
│   ├── Excel/
│   │   ├── job_advert_addon_summary_final.xlsx
│   │   └── table5_job_advert_curriculum_alignment.xlsx
│   ├── table1_normalised_index_by_country.csv
│   ├── table2_normalised_index_by_degree_level.csv
│   ├── table3_depth_scope_authenticity_by_country.csv
│   ├── table4_reliability_factor_structure.csv
│   ├── table5_ols_regression.csv
│   ├── table6_mixed_model.csv
│   └── table7_robustness_checks.csv
├── README.md
├── README_replication_package.md
└── requirements.txt
```

File names are more stable than manuscript table numbers. If table numbers change during revision, use the file titles and descriptions rather than numbers alone.

---

## Key data files

### Curriculum dataset

**File:** `Data/Python_in_Finance_Curriculum_scored.csv`

This is the main programme-level dataset. It contains one row per coded finance-related programme.

Important fields include:

- `Country`: country or jurisdiction of the programme.
- `University_Name`: university name.
- `Program_Name`: programme title.
- `Degree_Level`: degree label or level recorded from documentation.
- `Evidence_Type`: type of source used for coding.
- `Evidence_URL`: public source URL where available.
- `Python_Found`: whether Python was explicitly documented.
- `Depth`: vertical integration score, 0 to 4.
- `Scope`: horizontal spread score, 0 to 4.
- `Authenticity`: assessed, real-world, finance-specific score, 0 to 4.
- `Python_Index`: `Depth + Scope + Authenticity`.
- `Python_Index_Normalised`: `Python_Index / 12`.
- `graduate_program`: binary indicator used in exploratory modelling.
- `Comments`: coder notes explaining how Python appears in the curriculum.

### Job-advert skill-signal dataset

**File:** `Data/JobAdvert/job_ads_coded_for_table5.csv`

This supplementary file contains 190 coded job-advert records, with 10 records per country. It is designed to provide an employer-facing comparator for data-intensive finance roles.

Important fields include:

- `country`: country associated with the advert.
- `job_title`: role title.
- `employer_type`: employer classification.
- `role_family`: finance, FinTech, data, risk, or quantitative role family.
- `python_flag`, `sql_flag`, `r_flag`: programming-language indicators.
- `ml_ai_flag`, `data_analytics_flag`: ML, AI, or data-analytics indicators.
- `risk_modeling_flag`, `portfolio_flag`, `algo_trading_flag`: finance-specific computational indicators.
- `programming_required_flag`, `programming_preferred_flag`: required or preferred programming signals.
- `job_algorithmic_skill_index`: mean of eight binary skill indicators.
- `curriculum_index`: matching country-level curriculum Python index.

---

## Quick start

### 1. Install requirements

Use Python 3.9 or later.

```bash
pip install -r requirements.txt
```

If you prefer to install manually:

```bash
pip install pandas numpy scipy statsmodels matplotlib openpyxl
```

### 2. Run the replication script

From the package root:

```bash
cd "Replication_When Finance Speaks Python"
python Code/replication_analysis.py
```

The script reads the curriculum dataset and regenerates outputs in:

```text
Tables/
Figures/
Appendices/
```

Running the script may overwrite generated CSV, TXT, and PNG outputs. The supplementary Excel workbooks in `Tables/Excel/` are included for inspection and reporting; they are not regenerated by the main curriculum script.

---

## Output guide

| Output | Location | Purpose |
|---|---|---|
| Country index table | `Tables/table1_normalised_index_by_country.csv` | Country-level curriculum Python index |
| Degree-level table | `Tables/table2_normalised_index_by_degree_level.csv` | Python adoption by degree label or level |
| Depth-Scope-Authenticity table | `Tables/table3_depth_scope_authenticity_by_country.csv` | Country-level rubric profile |
| Reliability and factor structure | `Tables/table4_reliability_factor_structure.csv` | Scale diagnostics for the index |
| OLS regression | `Tables/table5_ols_regression.csv` | Exploratory graduate-programme association |
| Mixed model | `Tables/table6_mixed_model.csv` | Model including country random intercept |
| Robustness checks | `Tables/table7_robustness_checks.csv` | Additional analytic checks |
| Job-advert alignment Excel | `Tables/Excel/table5_job_advert_curriculum_alignment.xlsx` | Employer-facing skill signals and curriculum gap |
| Job-advert summary Excel | `Tables/Excel/job_advert_addon_summary_final.xlsx` | Supplementary job-advert summary output |
| Country figure | `Figures/figure2_mean_index_by_country.png` | Cross-national curriculum index visualization |
| Rubric profile figure | `Figures/figure3_depth_scope_authenticity_by_country.png` | Depth, Scope, Authenticity by country |

---

## Interpretation guardrails

Please use the package with the same guardrails used in the manuscript.

1. **Documented curriculum is not the same as classroom practice.** A programme may use Python in teaching without naming it in public materials.
2. **Low documentation is still meaningful.** Public documents shape what students, employers, regulators, and reviewers can see.
3. **The job-advert data are exploratory.** They show skill bundles in targeted data-intensive finance roles, not prevalence across all finance jobs.
4. **Country means are not national rankings.** Some countries have small programme counts, so country-level values should be interpreted as descriptive signals.
5. **Python is a proxy, not the whole computational stack.** Programmes may also use R, MATLAB, SQL, C++, Julia, spreadsheets, APIs, cloud tools, or specialist finance platforms.

---

## Checksums and file integrity

SHA-256 checksums are provided in:

```text
Documentation/checksums_sha256.txt
```

To verify the package on macOS or Linux:

```bash
shasum -a 256 -c Documentation/checksums_sha256.txt
```

On systems with GNU coreutils:

```bash
sha256sum -c Documentation/checksums_sha256.txt
```

---

## Ethics and data use

This study uses publicly available university programme materials and publicly visible job-advert information. No students, staff, or job applicants were recruited. No individual-level student or staff data are included. The analysis is designed to identify aggregate curriculum and skill-signal patterns, not to rank institutions or evaluate individual competence.

The replication package is suitable for scholarly review, reproducibility checks, and methodological adaptation. Any reuse should cite the package DOI and respect the original context of the public documents from which the data were coded.

---

## Suggested citation

Drakopoulou, V. (2026). *Replication package for Closing or Reproducing the Skills Gap? Python Integration in Finance Degrees and the University-Industry Interface* [Data set and code]. Zenodo. https://doi.org/10.5281/zenodo.18713524

---

## Contact

For questions about the dataset, code, or replication package, contact:

**Veliota Drakopoulou**  
Email: vdrakopoulou@yahoo.com  
ORCID: https://orcid.org/0000-0002-1670-8033  
GitHub: https://github.com/vdrakopoulou
