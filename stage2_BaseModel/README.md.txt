## Folder Structure 
An overview of structure of this submission folder is shown below. It is followed by a detailed explanation of each sub-folder and file.
```
├── README.md            
├── data       
│   ├── processed     
│   ├── raw           
│   └── experiments   
│
├── notebooks
│   └── dataPreProcessing.ipynb  
│   └── Analysis.ipynb 
│
├── model
│   └── README.md 
│   └── model.py 
│   └── components.py  
│   └── model_run.py    
│   └── model_viz.py.   
│   └── batch_run.py   
│
├── report
│   └── EPA1352-G17-A2-Report.pdf   
│   └── figures 
│
├── requirements.txt  
```
 **Data**:
 - The 'raw' folder contains all data files as downloaded from Brightspace. The .csv files can be used to run demos of the model. The files "_roads3.csv" and "BMMS_overview.xlsx" are the base for the "N1.csv" file we create after some data cleaning in the python file "preprocessing.ipynb".  
 - The 'processed' folder contains the "N1.csv" file used to run the model. 
 - The "experiments" folder contains all .csv files created after running all scenarios consecutively as per assignment instructions with "batch_run.py"
 
**Notebooks**:  This folder contains files for the cleaning process and the analysis.
- preprocessing.ipynb describes the cleaning of data and the creation of the "N1.csv" file. 
- Analysis.ipynb creates all figures present in the "report/figures" sub-folder 

**Model**:  This folder contains all files regarding the model and its execution
- model.py is the model
- components.py contains the modified agent classes used by model.py
- model_run.py runs the model 
- model_viz.py runs the visualization of the model 
- batch_run.py runs all scenarios consecutively 

**requirements.txt**: This file contains all of the requirements your python environment should fulfil in order to reproduce the analysis environment.


