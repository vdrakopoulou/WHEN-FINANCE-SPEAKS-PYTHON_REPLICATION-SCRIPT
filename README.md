# WHEN-FINANCE-SPEAKS-PYTHON_REPLICATION-SCRIPT



README – Replication Code

Project: Algorithmic Stratification in Finance Degrees: Global Patterns of Python Adoption in University Curricula
Author: Veliota Drakopoulou
Affiliations:
¹ Higher Colleges of Technology
² Embry‑Riddle Aeronautical University

ORCID: 0000‑0002‑1670‑8033
Correspondence: vdrakopoulou@yahoo.com

GitHub: https://github.com/vdrakopoulou


1. Overview

This repository contains a single script that reproduces all quantitative results from the scored curriculum dataset:



Script: replication_analysis.py

Main data file: Data/Python_in_Finance_Curriculum_scored.csv 

replication_analysis

Running the script will regenerate:

Tables 1–7 (CSV) in /Tables/

Figures 2–3 (PNG) in /Figures/

Appendix tables A1–A2, B1–B2, C1–C2, D1–D2 (CSV) in /Appendices/

The script also writes brief ANOVA and model summaries as .txt files in /Tables/.

2. Folder structure

Expected structure:

replication_Q1/
    replication_analysis.py
    Data/
        Python_in_Finance_Curriculum_scored.csv
    Tables/
    Figures/
    Appendices/

The script will create Tables/, Figures/ and Appendices/ if they do not exist.

3. Requirements

Python: 3.x

Packages:

pandas

numpy

matplotlib

statsmodels

scipy

Install (example):

pip install pandas numpy matplotlib statsmodels scipy
4. How to run

From inside the root folder (e.g., replication_Q1/):

python replication_analysis.py

If Data/Python_in_Finance_Curriculum_scored.csv is present and has the required columns, the script will:

Load the dataset.

Compute descriptive statistics and ANOVA by country.

Estimate:

OLS model (Python index ~ graduate_program).

Mixed‑effects model with random intercepts by country (if ≥ 2 countries).

Save all tables, figures and appendix files into their respective folders.

A short completion message is printed to the console indicating where outputs were written.

5. Outputs (summary)

Tables/

table1_normalised_index_by_country.csv (+ table1_anova.txt)

table2_normalised_index_by_degree_level.csv

table3_depth_scope_authenticity_by_country.csv

table4_reliability_factor_structure.csv

table5_ols_regression.csv (+ table5_ols_summary.txt)

table6_mixed_model.csv (+ table6_mixed_model_summary.txt)

table7_robustness_checks.csv

Figures/

figure2_mean_index_by_country.png

figure3_depth_scope_authenticity_by_country.png

Appendices/

appendix_A1_sample_by_country.csv

appendix_A2_sample_by_degree_level.csv

appendix_B1_rubric_definitions.csv

appendix_B2_rubric_examples.csv

appendix_C1_descriptives_key_variables.csv

appendix_C2_correlation_matrix.csv

appendix_D1_full_ols_regression.csv

appendix_D2_mixed_effects_parameters.csv

6. Contact

For questions about the replication code or data, please contact:

 

Veliota Drakopoulou
📧 vdrakopoulou@yahoo.com
