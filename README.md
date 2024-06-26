# IPZ-Regresija
Kreiranje modela mašinskog učenja za regresiju korišćenjem Weka alata.
## Dataset
Korišćen je [dataset](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction) koji sadrži podatke o cenama avionskih karata
## Priprema podataka

- **Brisanje atributa** Brisanje atributa serial_number jer ne doprinosi treniranju modela ![Delete attribute](Slike/RemoveSeralNumber.png)

- **Random podskup podataka** *weka.filters.unsupervised.instance.ReservoirSample* Produces a random subsample of a dataset using the reservoir sampling Algorithm "R" by Vitter 
The original data set does not have to fit into main memory, but the reservoir does. ![Random podskup](Slike/ReservoirSampleSettings.png)


## Regresija Correlation coefficient

- *funtions.LinearRegression* 
	- cross validation 10 folds 0.9483
	- 80-20 split 0.9399
	- 60-40 split 0.947
- *lazy.IBk (KNN=3)*
	- cross validation 10 folds 0.8774
	- 60-40 spli 0.8648
	- 80-20 split 0.8686
- *lazy.IBk (KNN=7)*
	- cross validation 10 folds 0.7941
	- 80-20 split 0.8958%
	- 60-40 spli 0.895%
- *lazy.IBk (KNN=11)*
	- cross validation 10 folds 0.9163
	- 60-40 spli 0.9147
	- 80-20 split 0.908
*lazy.IBk (KNN=21)*
	- cross validation 10 folds 0.9356
	- 60-40 spli 0.9318
	- 80-20 split 0.9306
- *trees.M5P*
	- cross validation 10 folds 0.966 
	- 80-20 split 0.9594

M5P daje najveću tačnost od svih isprobanih klasifikatora. 

## Rezultati
Correlation coefficient                  0.966 
Mean absolute error                   3567.8696
Root mean squared error               5809.4104
Relative absolute error                 18.2784 %
Root relative squared error             25.9018 %
Total Number of Instances             2000   



- **Normalizacija podataka** *weka.filters.unsupervised.attribute.Normalize* sa scale na 1.0 i translation 0.0 koji normalizuje numeric vrednosti atributa na opseg 0-1![Normalize](Slike/Normalize.png)

- *trees.M5P*
	- cross validation normalized 10 folds 0.9555 
	- 80-20 split normalized 0.9594

- *funtions.LinearRegression* 
	- cross validation 10 folds 0.9401
	- 80-20 split 0.948 






