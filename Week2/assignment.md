# Assignment for Week 2 

## MLOps Assignment Github repo link :
```
https://github.com/SarthakM320/MLOps_Assignment
```
## Steps used to accomplish this assignment:
```
# Making a Folder
mkdir MLOps_Assignment
cd MLOps_Assignment

# Initializing git repo
git init
git remote add origin https://github.com/SarthakM320/MLOps_Assignment
git branch -M main

# Initializing DVC
dvc init

# Then the data was downloaded and added

dvc add data/creditcard.csv
git add data/creditcard.csv.dvc data/.gitignore
git commit -m "Data added"

dvc remote add -d storage s3://mlopsassignment2/datastore
git add .dvc/config
git commit -m "Storage added"
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

git commit -m "Model and metrics added"

dvc push
git push origin expt2_rf



```


