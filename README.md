###  Coding/Work Environments & Pipelines
#### **Github**:
This will allow coding collaboration to happen and feedback on code. 
- *Folder Structure*: inspiration taken from [AP Datakit](https://github.com/associatedpress/cookiecutter-r-project)

	```
	+-- analysis
	| +-- archive		
	+-- data
	| +-- documentation
	| +-- handmade
	| +-- html_reports
	| +-- processed
	| +-- public
	| +-- source
	+-- etl
	+-- publish	
	+-- webscrapers
	+-- viz
	```
- *Brief Explanation*
	- **analysis**
		R code on already cleaned data. Code that cleaned the data goes in **etl** folder
		- Make a new R markdown script for each "theme" or investigative goal
		- **analysis/archive**: Put any analysis directions that are not longer being investigated into this folder
	- **data**
		*IMPORTANT*: every data file should be labeled with eiother
			- the date range that the data covers **or**
			- the date that the data was downloaded
		This will be allow us to see what analysis use what data when datasets are updated by agencies 
		- **data/documentation:** each dataset that appears in the data directory should have a corresponding .md file. The .md file will include a section for a data dictionary, known caveats, and questions that still need to be answered. 
		- **data/handmade**: manually created data sets go here, or pulled data from web scrapers
		- **data/html_reports**: html_reports or pages generated by code go here. These html reports can be shared with reporters, and should have google sheet links to the data that we want reporters to have easy access to. Here is a still [in-progress style guide for R Markdown html_reports](https://docs.google.com/document/d/1Tn0rCnDjTtZDky_q3Dx77Yn3vCQ8TJc_9Luub_oMHO4/edit)]
		- **data/processed**: data that has been processed by etl scripts is exported in either .csv or .rds format here. 
		- **data/source**: original data from sources go here
	- **etl (extract, transform, load)**
		- R markdown scripts for reading in data from **data/source** and cleaning it or joining it to other data sets
		- Last step is to output a .csv or .rds to **data/processed**
			- naming convention: etl_WHATEVERNAME_date.rds
	- **publish**
		- This directory contains the final RMarkdown files for our published fact check documents that we release at the end of the investigation
		- **webscrapers**
			- This directory contains webscrapers for data acquisition 
	- **viz**
		- If in the future we create Shiny apps, that work would go here

