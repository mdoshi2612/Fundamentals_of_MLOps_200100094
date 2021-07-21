# Assignment for Week 2 

## MLOps Assignment Github repo link :
```
https://github.com/mdoshi2612/MLOps_Assignment
```
## Steps used to accomplish this assignment:
```
# Making a Folder
mkdir mlops_assignment
cd mlops_assignment

# Initializing git repo
git init
git remote add origin https://github.com/mdoshi2612/MLOps_Assignment
git branch -M main

# Initializing DVC
dvc init

# Then the data was downloaded and added

dvc add data/creditcard.csv
git add data/creditcard.csv.dvc data/.gitignore
git commit -m "Added data"

dvc remote add -d storage s3://mlops200100094/datastore
git add .dvc/config
git commit -m "Setting up remote storage"
dvc push
git push origin main

mkdir models
mkdir src
mkdir metrics
mkdir data/preprocessed

git checkout -b expt1_dt
touch expt.py

dvc add models/model.pkl
git add models/model.pkl.dvc models/.gitignore

dvc add metrics/acc_f1.json
git add metrics/acc_f1.json.dvc metrics/.gitignore

dvc add data/preprocessed
git add data/preprocessed.dvc data/.gitignore
git add src/
git commit -m "Model and metrics added"


dvc push
git push origin expt1_dt

git checkout -b expt2.rf
dvc add models/model.pkl
git add models/model.pkl.dvc models/.gitignore

dvc add metrics/acc_f1.json
git add metrics/acc_f1.json.dvc metrics/.gitignore

dvc add data/preprocessed
git add data/preprocessed.dvc data/.gitignore
git add src/
git commit -m "Model and metrics added"

dvc push
git push origin expt2_rf



```


## Values
 - Decision tree Classifier :
   - F1 Score - 0.7976878613 
   - Accuracy - 0.9993855445
 - Random Forest Classifier:
   - F1 Score - 0.8275862069
   - Accuracy - 0.9994733239


## Screenshots Of S3 Bucket
![image](https://github.com/mdoshi2612/Fundamentals_of_MLOps_200100094/blob/main/Week2/2021-07-21.png)
![image](https://github.com/mdoshi2612/Fundamentals_of_MLOps_200100094/blob/main/Week2/2021-07-21%20(2).png)
