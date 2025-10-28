# General Workflow 
1. Please edit the fields in the config_template.json file.
  - "site_name" should be your site
  - "output_path" should be local working directory folder
  - "tables_path" should be where your CLIF_.parquet files are located
  - "file_type" is parquet
3. Save the updated config_template.json file as config.json in a folder called "config" in your local directory - see below for additional info
4. Run config.R

Recommend your local directory should look like:  

| Name of your local working directory folder  
    |- config (folder)  
        |- config.json 
        |- config.R    
|- 01_valid_hosp_ASE.Rmd  
|- 02_heat_map_naming_updated.Rmd  
|- 03_Histograms.Rmd  
|- 04_stepwise_odds_ratio.Rmd  
|- 05_quick_table.Rmd  
|- intermediate (folder)  
|- outputs (folder)  
