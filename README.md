# MR_preproc_dash
Dashboard to monitor MR image preproc pipeline status

**Basic workflow**
- run preproc status script anytime after preproc job has been submitted 
- status script
    - input: path to preproc dir containing all the subject subdirectories, save_path to dump summary csv
    - optional input: subject metadata, demographic info etc. 
- checks preproc output directory tree
    - timepoint dirs (per subject)
    - MR output dirs (per timepoint)
    - MR mnc files (per output dir) 
- log parser (in progress)
    - read logs for troubleshooting
    
**Code structure**
- ./lib : useful defs
- ./notebook/MR_preproc_dash_test_code.ipynb: test-run notebook (This will produce color-coded dataframes!!) 
- ./run_test.py command-line code (This will dump summary data to a csv) 
    
**Examples**
- source /ipl/quarantine/experimental/2013-02-15/init.csh (at BIC) 
- run_test.py:  python run_test.py --data_dir /data/ipl/scratch03/nikhil/MR_preproc_dash/mahsa_preproc_test_data/ --save_path /data/ipl/scratch03/nikhil/MR_preproc_dash/preproc_dash.csv


**prerequisites** 
- python 3+ 
- pandas 
- https://github.com/vfonov/nist_mni_pipelines (needs iplPatient.py in PYTHONPATH)
