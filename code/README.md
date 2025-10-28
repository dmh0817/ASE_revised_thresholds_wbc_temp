# Code Directory   

## General Workflow  

* Before beginning:
    * Ensure your config.json files has been updated and saved  
    * Ensure config.R has been run
      
_________________________

# Run [01_valid_hosp_ASE.Rmd](code/01_valid_hosp_ASE.Rmd)  
### This script should:  
* Define valid hospitalizations by inclusion / exclusion criteria
* Identify patients meeting [ASE Criteria](https://stacks.cdc.gov/view/cdc/132387)
* Add an ase_flag to any valid hospitalizations meeting ASE criteria

### Input
* CLIF tables: hospitalization, patient, adt, labs, vitals, microbiology_culture, medication_admin_intermittent, medication_admin_continuous, respiratory_support

### Expected Output
* intermediate tables (should not be shared across sites)

_________________________

# Run [02_heat_map_naming_updated.Rmd](code/02_heat_map_naming_updated.Rmd)  
### This script should:  
* Create Youden-Index heatmaps for WBC and Temperature based on ase_flag (sepsis cases)

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)

### Expected Output
* sitename_heatmap_temp_Sys.Date().png saved to "outputs" folder
* sitename_heatmap_wbc_Sys.Date().png saved to "outputs" folder

_______________________

# Run [03_Histograms.Rmd](code/03_Histograms.Rmd)  
### This script should:  
* Create histograms of ase-prevalence by interval based on ase_flag (sepsis cases)

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)

### Expected Output
* sitename_histogram_temp_Sys.Date().png saved to "outputs" folder
* sitename_histogram_wbc_Sys.Date().png saved to "outputs" folder

_______________________

# Run [04_stepwise_odds_ratio.Rmd](code/04_stepwise_odds_ratio.Rmd)  
### This script should:  
* Create stepwise odds-ratios (forward and backward) for temp and WBC based on ase_flag (sepsis cases)

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)

### Expected Output
* sitename_stepwiseOR_temp_Sys.Date().png saved to "outputs" folder
* sitename_stepwiseOR_wbc_Sys.Date().png saved to "outputs" folder

_______________________

# Run [05_quick_table.Rmd](code/05_quick_table.Rmd)  
### This script should:  
* Create a basic table with patient demographics 

### Input
* master_list (created in 01_valid_hosp, saved down in "intermediate" folder)
* CLIF tables: patient, hospitalization 

### Expected Output
* sitename_table1_Sys.Date().pdf saved to "outputs" folder
