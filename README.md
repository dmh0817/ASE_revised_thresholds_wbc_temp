# ASE Revised Thresholds for WBC and Temperature
Optimized WBC and temp thresholds for early sepsis detection

# Project Overview:
Traditionally accepted ranges for white blood cell (WBC) counts (4 – 12 x10⁹/L) and temperature (36 - 38°C) in sepsis were originally derived from expert consensus in the early 1990s and continue to play a prominent role in driving suspicion of potential sepsis cases and associated clinical decision making. 

**Our aim is to evaluate optimized WBC and temperature thresholds using real-world, large-scale EHR data**. For this project, sepsis is defined using the CDC Adult Sepsis Event (ASE) criteria which requires:
1. A presumed serious infection as evidenced by blood culture collection and a minimum of four consecutive days of antibiotics (some exceptions for discharge locations / expiration)
2. Evidence of end organ dysfunction.
   
This study limited sepsis cases to community acquired sepsis.

# Data Sources
### Sites: 
Sites must have non-ICU data
### Study Period:
Admission times between 01-01-2024 to 03-01-2025, inclusive  

# Required CLIF tables
The following tables are required:
1. hospitalization: patient_id, hospitalization_id, admission_dttm, discharge_dttm, age_at_admission, discharge_category
2. adt: hospitalization_id, location_category
3. labs: hospitalization_id, lab_order_dttm, lab_value, lab_value_numeric, lab_category, lab_result_dttm
4. vitals: vital_category, vital_value, recorded_dttm
5. microbiology_culture: fluid_category, order_dttm, organism_name
6. medication_admin_intermittent: med_group, med_name, admin_dttm
7. medication_admin_continuous: med_group, admin_dttm
8. respiratory_support: device_category, recorded_dttm
9. patient_assessments: assessment_category, recorded_dttm, numerical_value 

# Inclusion Criteria:
- Age >= 18 years at time of admission
- Admission time between 01/01/2024 - 03/01/2025 (inclusive)
- Admitted to wards or ICU during hospitalization
- WBC and temperature logged within 24 hours of admission

# Exclusion Criteria:
- ED visit only (no admission to wards or ICU)

# Instructions for running project:

Before beginning, recommend your set up looks like:

project-root/  
├── config/  
│ ├── config.json – Primary configuration file containing site name, paths  
│  
├── code/   
│ ├── 00_set_up.Rmd – Initializes environment, loads packages, and reads configuration  
│ ├── 01_valid_hosp_ASE.Rmd – Defines valid hospitalizations and identifies ASE cases  
│ ├── 02_heat_map_naming_updated.Rmd – Generates Youden Index heatmaps  
│ ├── 03_Histograms.Rmd – Creates WBC and temperature ASE-prevalence histograms  
│ ├── 04_stepwise_odds_ratio.Rmd – Runs stepwise odds ratio analyses and plots results  
│ ├── 05_quick_table.Rmd – Builds and exports basic Table 1 summary statistics  
│  
├── intermediate/ – Intermediate data files and derived datasets  
├── outputs/ – Final plots, tables, and reports  

# Now to run the project:
1. Update the config_template.json to config.json
2. Run code in numerical order
3. Upload outputs to Box folder (instructions in outputs README)
