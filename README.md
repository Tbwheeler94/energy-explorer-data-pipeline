# **Welcome to the energyexplorer.io data pipeline!**

### **README.md purpose**

This document provides an overview of the project background, key files, and additional data sources used in developing this project. *data-pipeline.ipynb* is an interactive notebook which provides a way for a user to understand the backend calculations used by energyexplorer.io.

### **How to explore the data pipeline?**

Open up *data-pipeline.ipynb*! Directions are embedded into the notebook so you can just follow along.

### **Project overview**

energyexplorer.io was developed to automate the steps I took to complete a homework assignment from and Energy & Electric Power Markets course I took in pursuit of completing my master's degree in environmental science & management at University of California, Santa Barbara.

### **Key files**

*data-pipeline.ipynb:* This [jupyter notebook](https://jupyter.org/) provides a step by step journey to interact with and understand the data import and calculations behind the energyexplorer.io dashboard \


*/data/LMP_Historic_Price.csv:* This is an example dataset of historical hourly locational marginal pricing at the HOLLISTR_1_N101 wholesale node for the year 2020 near Hollister, California. In the 1.0.0 version of energyexplorer.io this is the dataset used for all future price calculations and was manually downloaded by me using [California Independent System Operator's (CAISO)](https://www.caiso.com/Pages/default.aspx) [OASIS](http://oasis.caiso.com/mrioasis/logon.do) tool. \


*/data/LMPLocations.csv:* This is a dataset of all load and generation nodes operating under CAISO's jurisdiction. This dataset is used to find the nearest wholesale node to the requested solar plant location. This dataset was provided by another project [CAISO Scraper](https://github.com/emunsing/CAISO-Scrapers/blob/master/LMP%20Location%20Scraper/LMPLocations_vs_FullList.xls).

### **Organizations and data sources used in completion of this project**

Solar resource: National Solar Radiation Database (NSRDB) (https://nsrdb.nrel.gov/) \

Wind resource: Wind Toolkit (https://www.nrel.gov/grid/wind-toolkit.html) \

Costs: NREL’s Annual Technology Baseline (https://atb.nrel.gov/) and Lazard’s LCOE
estimates \

Wholesale electricity prices (Locational marginal prices): ISO websites e.g. CAISO
(oasis.caiso.com), ERCOT. \

NREL’s System Advisor Model (SAM) to estimate hourly wind and solar PV generation:
https://sam.nrel.gov/ \

NREL’s Cambium tool: https://www.nrel.gov/analysis/cambium.html (used in original hw assignment, not in this project) \

Federal Energy Management Program (FEMP) screening map:
https://maps.nrel.gov/femp/ (used in original hw assignment, not in this project) \