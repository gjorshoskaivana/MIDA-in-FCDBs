# Multiple value imputation using Denoising Autoencoders in Food Composition Databases

## Abstract

Missing data is a common problem in a wide range of fields that can arise as a result of different reasons: lack of analysis, mishandling samples, measurement error, etc. The area of nutrition and food composition is no exception to the problem of missing values. Missing data in food composition databases (FCDB) significantly limits their usage. Commonly this problem is resolved by calculating mean or median from available data in the same FCDB or borrowing values from other FCDBs, however, this method produces notable errors. We focus on missing value imputation using autoencoders, a deep learning algorithm that has the ability to approximate values by learning a higher-level representation of its input. The data used was from the FCDBs collected by the USDA FoodData Central. We compared the autoencoder imputation method with the commonly used approaches fill-in-with-mean and fill-in-with-median, and the results show that the autoencoder method for imputation provides superior results.

## Requirements

Required libraries to run the notebooks can be found in [requirements.txt](requirements.txt). 

## Data used in the experiments

### Statistics about the original data taken from FoodData Central

Code can be found in [statistics_original_data.ipynb](statistics_original_data.ipynb). The original datasets can be found in [datasets/original data](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/original%20data). 

### Reconstructed datasets from the original dataset in a format such that every sample is a vector of nutrient values for one food sample

Code can be found in [converting_the_datasets_and_column_sort.ipynb](converting_the_datasets_and_column_sort.ipynb). The newly constructed datasets are available in [datasets/average datasets/byColumns](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/average%20datasets/byColumns) that contains the datasets of the average nutrient values and [datasets/median datasets/byColumns](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/median%20datasets/byColumns) that contains the datasets of the median nutrient values. 

### Making sentence embeddings for the food items and appending them to the converted datasets

Code can be found in [datasets_word_embeddings.ipynb](datasets_word_embeddings.ipynb). The final datasets can be found in [datasets/average datasets/byColumnsWithEmbeddings](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/average%20datasets/byColumnsWithEmbeddings) containing the average value datasets and [datasets/median datasets/byColumnsWithEmbeddings](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/median%20datasets/byColumnsWithEmbeddings) containing the median value datasets. 

### Datasets containing calculated mean and median values for each food item according to food category

Code can be found in [mean_median_by_category_datasets.ipynb](mean_median_by_category_datasets.ipynb). The final datasets can be found in [datasets/average datasets/traditionalMethods](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/average%20datasets/traditionalMethods) and [datasets/median datasets/traditionalMethods](https://github.com/gjorshoskaivana/MIDA-in-FCDBs/tree/master/datasets/median%20datasets/traditionalMethods) accordingly. 

## Autoencoder experiments
There are separate Jypiter notebooks for the experiments using nutrient average values and median values. Each notebook can be run independently. Furthermore, within the notebooks there is a section dedicated to each use case explained in the paper. Each of these sections can be run independently of each other, as long as the sections "Import libraries", "Missingness method", "Imputation Methods", "Evaluation" and "Data Preparation" have been previously run. 

To re-produce the experiments using the average nutrient value datasets, run [autoencoder_averageValues.ipynb](autoencoder_averageValues.ipynb). 

To re-produce the experiments using the median nutrient value datasets, run [autoencoder_medianValues.ipynb](autoencoder_medianValues.ipynb). 

## References

The original datasets used in the experiments are table found in Foundation Foods data type. Reference to the data:

U.S. Department of Agriculture, Agricultural Research Service. FoodData Central, 2021. [fdc.nal.usda.gov](https://fdc.nal.usda.gov/).
