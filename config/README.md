# General Workflow 
1. Please edit the fields in the config_template.json file with your site specific information.
  - "site_name" should be your site
  - "output_path" should be local working directory folder
  - "tables_path" should be where your CLIF_.parquet files are located
  - "file_type" is parquet
3. Save the updated config_template.json file as config.json in a folder called "config" in your local directory - see below for additional info


Recommend your local directory should look like:  

project-root/
├── config/
│ ├── config.json – Primary configuration file containing site name, paths
│
├── 00_set_up.Rmd – Initializes environment, loads packages, and reads configuration
├── 01_valid_hosp_ASE.Rmd – Defines valid hospitalizations and identifies ASE cases
├── 02_heat_map_naming_updated.Rmd – Generates Youden Index heatmaps
├── 03_Histograms.Rmd – Creates WBC and temperature ASE-prevalence histograms
├── 04_stepwise_odds_ratio.Rmd – Runs stepwise odds ratio analyses and plots results
├── 05_quick_table.Rmd – Builds and exports basic Table 1 summary statistics
│
├── intermediate/ – Intermediate data files and derived datasets
├── outputs/ – Final plots, tables, and reports
