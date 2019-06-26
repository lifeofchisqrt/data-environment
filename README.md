# data-environment
My data science environment setup - docker files, pip requirements, configs etc.

## Current setup
Currently I'm running docker container starting Jupyter Lab with scipy/anaconda stack of python packages and pyspark.  
This docker has mounted volume to ~/shared folder on my local machine which contains folders:  
 - /data : raw data files, input data to models  
 - /notebooks : jupyter notebooks  
 - /models : serialized models  
 - /misc : config files, binaries etc.  

### Docker:
  1. juno: Jupyter Lab image lifeofchisqrt/juno:juno_01  
    - based on jupyter/pyspark-notebook  
    - by default includes scipy stack with python3 and pyspark  
    - additional packages in requirements.txt (tensorflow, imblearn, nltk)  
    - jupyter_notebook_config.py - starts locally with no token, just hashed, required password  
    - includes few jupyter_lab extensions - qgrid, toc, snippets, variables inspector
  2. mlflow (work in progress):  
    - image with Databricks MLFlow for automated model training, logging (and potential deployment?)  
  3. spark (work in progress):  
    - image running Apache Spark on standalone (local) node  

### Running Docker Container:
  1. docker run -t -i -p 8890:8888 lifeofchisqrt/juno:juno_01

#### TO DO:
- require jupyter_config file when creating image or create password
- setup AWS S3 bucket for data download/upload or buy 1T SSD  
- convert /data to ORC/Parquet HDFS


