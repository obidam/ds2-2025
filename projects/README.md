# Projects guideline

## Github Procedure
- Fork this github repository to your own account
- Add a folder under ds2-2025/projects, name it with your group last names
- Work out your project codes/documentation and stage/push it to your folder on your fork
- Once finalized, create a pull request to the main branch

## Project 5 and 6

### Computation set-up

Please follow instructions from: https://github.com/obidam/ds2-2025/blob/main/practice/environment/coiled/README.md 

### Project 5: Ocean warming
 
Get all the details and a starter notebook here:
https://github.com/obidam/ds2-2025/blob/main/projects/help/P5-OceanWarming-for-students.ipynb

### Project 6: Ocean thermal and haline change contributions to Sea Level trends
 
Get all the details and a starter notebook here:
https://github.com/obidam/ds2-2025/blob/main/projects/help/P6-OceanWarmingSeaLEvel-for-students.ipynb

## Projects 7 and 8: Future Arctic sea ice change (Arctic) / the Atlantic Multidecadal Oscillation

*Description*: The Coupled Model Intercomparison Project is a framework within which a number of research centres produce predictions of the future evolution of the climate. Many climate centres use an ensemble approach, in which they produce several simulations for each scenario, using the same model configuration. By comparing these multiple simulations (“the ensemble"), we can estimate the probability that the climate will evolve in a certain way.

*Data*: Google host a part of these data via their Public Datasets programme (https://cloud.google.com/blog/products/data-analytics/new-climate-model-data-now-google-public-datasets).

This dataset can be accessed this way:

	df = pd.read_csv('https://storage.googleapis.com/cmip6/cmip6-zarr-consolidated-stores.csv')
	df_ssh = df.query("activity_id=='ScenarioMIP' & table_id == 'Omon' & variable_id == 'zos' & institution_id == 'IPSL'")
	gcs = gcsfs.GCSFileSystem(token='anon')
	zstore = df_ssh.zstore.values[-1]
	mapper = gcs.get_mapper(zstore)
	ds = xr.(mapper, consolidated=True)

Notebook with info on the CMIP experiments and example code for project 7, future Arctic sea ice: [![Colab](https://img.shields.io/static/v1?label=Google&message=Open+data+with+Colab&color=blue&style=plastic&logo=google-colab)](https://colab.research.google.com/github/obidam/ds2-2025/blob/main/project/Information_for_project_7%2C_Future_Arctic_Sea_Ice%2C_2025.ipynb)

Notebook with info on the CMIP experiments and example code for project 8, the Atlantic Multidecadal Oscillation: [![Colab](https://img.shields.io/static/v1?label=Google&message=Open+data+with+Colab&color=blue&style=plastic&logo=google-colab)](https://colab.research.google.com/github/obidam/ds2-2025/blob/main/project/Information_for_project_8%2C_the_Atlantic_Multidecadal_Oscillation.ipynb)
***
<img src="https://github.com/obidam/ds2-2025/raw/main/logo_isblue.jpg">
