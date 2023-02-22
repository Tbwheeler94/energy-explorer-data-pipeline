# **Welcome to the energyexplorer.io data pipeline!**

### **README.md purpose**

This document provides an overview of the project background, key files, and additional data sources used in developing this project. *data-pipeline.ipynb* is an interactive notebook which provides a way for a user to understand the backend calculations used by energyexplorer.io.

### **How to explore the data pipeline?**

Open up *data-pipeline.ipynb*! Directions are embedded into the notebook so you can just follow along.

### **Project overview**

energyexplorer.io was developed to automate and visualize a homework assignment from the [Electric Power Systems & Markets](https://bren.ucsb.edu/courses/esm-293-1s) course taught by [Professor Ranjit Deshmukh](https://bren.ucsb.edu/people/ranjit-deshmukh) at the Bren School of Environmental Science & Management, University of California, Santa Barbara. I took this course while pursuing a Master's of Environmental Science & Management degree.

### **Key files**

*data-pipeline.ipynb:* This [jupyter notebook](https://jupyter.org/) provides a step by step journey through the data imports, calculations, and outputs behind the energyexplorer.io dashboard.


*/data/LMP_Historic_Price.csv:* This is a dataset of historical hourly locational marginal pricing (LMP) at the HOLLISTR_1_N101 wholesale node for the year 2020 near Hollister, California. In the current version of energyexplorer.io, this is the dataset used for all future price calculations and was manually downloaded by me using [California Independent System Operator's (CAISO)](https://www.caiso.com/Pages/default.aspx) [OASIS](http://oasis.caiso.com/mrioasis/logon.do) tool (more about the tool below). In a future version of energyexplorer.io, LMP data will be pulled in programmatically to enable more accurate pricing forecasting.


*/data/LMPLocations.csv:* This is a dataset of all load and generation nodes operating under CAISO's jurisdiction. This dataset is used to find the nearest wholesale node to the requested solar plant location. This dataset was generated using a tool named [CAISO Scraper](https://github.com/emunsing/CAISO-Scrapers/blob/master/LMP%20Location%20Scraper/LMPLocations_vs_FullList.xls) developed by [Eric Munsing](https://www.linkedin.com/in/emunsing/) in partnership with the [Cleanweb](http://cleanweb.berkeley.edu/) group at UC Berkeley.

### **Organizations and data sources used in completion of this project**

[National Solar Radiation Database (NSRDB)](https://nsrdb.nrel.gov/)
- Database of hourly and half-hourly solar radiation (global horizontal, direct normal, and diffuse horizontal irradiance) across the United States and in some international locations. This dataset is accessed using NREL's [Python API](https://developer.nrel.gov/docs/solar/nsrdb/python-examples/).

[NREL’s System Advisor Model (SAM)](https://sam.nrel.gov/)
- SAM is a model used to calculate energy generation and financial projections for a variety of renewable energy systems. The current version of energyexplorer.io uses SAM's energy generation model to convert solar radiation data from NSRDB to energy generation by a solar plant with user defined parameters. This tool is accessed using the [NREL-PySAM package](https://pypi.org/project/NREL-PySAM/).

[CAISO OAIS](http://oasis.caiso.com/mrioasis/logon.do)
- Database of real-time and historical data related to the ISO transmission system and its Market, such as system demand forecasts, transmission outage and capacity status, market prices and market result data. Click [here](http://www.caiso.com/TodaysOutlook/Pages/prices.html) to view a realtime map of wholesale energy prices across California. As previously discussed, the current version of energyexplorer.io uses a static, one year hourly dataset from the HOLLISTR_1_N101 for all future price predictions. This dataset was manually extracted using the CAISO OASIS online downloader.

[U.S. Solar Photovoltaic System and Energy Storage Cost Benchmarks: Q1 2021](https://www.nrel.gov/docs/fy22osti/80694.pdf)
- This NREL report was used to define capex and fixed o&m parameters used to calculated the levelized cost of energy (LCOE) in energyexplorer.io. More about cost and performance parameters provided by NREL for electricity generating technologies can be found [here](https://atb.nrel.gov/electricity/2022/index).

[NREL’s Cambium Viewer](https://www.nrel.gov/analysis/cambium.html)
- Database and viewing tool developed by NREL to project future wholesale energy prices and marginal emission rates across the United States. Projections provided by Cambium were are not currently used in energyexplorer.io.