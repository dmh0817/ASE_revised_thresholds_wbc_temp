# Code Directory   

## General Workflow  

* Before beginning:
    * Ensure your config.json file has been updated and saved. See [config README](../config/README.md) for more details if needed  


_________________________

# Run [00_set_up.Rmd](00_set_up.Rmd)  
### This script should:  
* Install and load required packages  
* Initialize environment  
* Set up config

### Input
* config.json needs to be updated with site specific information before running

### Expected Output
* N/A
_________________________

# Run [01_valid_hosp_ASE.Rmd](01_valid_hosp_ASE.Rmd)  
### This script should:  
* Define valid hospitalizations by inclusion / exclusion criteria
* Identify patients meeting [ASE Criteria](https://stacks.cdc.gov/view/cdc/132387)
* Add an ase_flag to any valid hospitalizations meeting ASE criteria

### Input
* CLIF tables: hospitalization, patient, adt, labs, vitals, microbiology_culture, medication_admin_intermittent, medication_admin_continuous, respiratory_support

### Expected Output
* intermediate tables (should not be shared across sites)

_________________________

# Run [02_heat_map_naming_updated.Rmd](02_heat_map_naming_updated.Rmd)  
### This script should:  
* Create Youden-Index heatmaps for WBC and Temperature based on ase_flag (sepsis cases)

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)

### Expected Output
* sitename_heatmap_temp_Sys.Date().png saved to "outputs" folder
* sitename_heatmap_wbc_Sys.Date().png saved to "outputs" folder

_______________________

# Run [03_Histograms.Rmd](03_Histograms.Rmd)  
### This script should:  
* Create histograms of ase-prevalence by interval based on ase_flag (sepsis cases)

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)

### Expected Output
* sitename_histogram_temp_Sys.Date().png saved to "outputs" folder
* sitename_histogram_wbc_Sys.Date().png saved to "outputs" folder

_______________________

# Run [04_stepwise_odds_ratio.Rmd](04_stepwise_odds_ratio.Rmd)  
### This script should:  
* Create stepwise odds-ratios (forward and backward) for temp and WBC based on ase_flag (sepsis cases)

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)

### Expected Output
* sitename_stepwiseOR_temp_Sys.Date().png saved to "outputs" folder
* sitename_stepwiseOR_wbc_Sys.Date().png saved to "outputs" folder

_______________________

# Run [05_quick_table.Rmd](05_quick_table.Rmd)  
### This script should:  
* Create a basic table with patient demographics 

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)
* CLIF tables: patient, hospitalization 

### Expected Output
* sitename_table1_Sys.Date().pdf saved to "outputs" folder
* sitename_table1_Sys.Date().csv saved to "outputs" folder
