Codebook
================
## describing the variables

* subject: ID the subject who performed the activity for each window sample. Its range is from 1 to 30.
* activityname: the name of the activity
* featureTF: A feature of time domain signal or frequency domain signal (Time or Frequency)   
* featureBG: A feature of acceleration signal (Body or Gravity) 
* featureAG: A feature of measuring instrument (Accelerometer or Gyroscope) 
* featureJE: A feature of Jerk signal, the body linear acceleration and angular velocity were derived in time to obtain  this Jerk signals
* featureMAG: A feature of magnitude of the signals calculated using the Euclidean norm
* featuremeasure: A feature of measurement variable, the mean value or the standard deviation (mean or std)  
* featureaxis: A feature of 3-axial signals in the X, Y and Z directions (X,Y,Z)
* count: Count of data points used to compute average 
* average: Average of each variable for each activity and each subject 

## summary of the variables 

### subject     

* Min.   : 1.0
* 1st Qu.: 8.0 
* Median :15.5 
* Mean   :15.5 
* 3rd Qu.:23.0 
* Max.   :30.0 

### activityname






## dataset structure 

Classes `data.table' and 'data.frame':	11880 obs. of  11 variables:
 $ subject       : int  1 1 1 1 1 1 1 1 1 1 ...
 $ activityname  : Factor w/ 6 levels "LAYING","SITTING",..: 1 1 1 1 1 1 1 1 1 1 ...
 $ featureTF     : Factor w/ 2 levels "Time","Frequency": 1 1 1 1 1 1 1 1 1 1 ...
 $ featureBG     : Factor w/ 3 levels NA,"Body","Gravity": 1 1 1 1 1 1 1 1 1 1 ...
 $ featureAG     : Factor w/ 2 levels "Accelerometer",..: 2 2 2 2 2 2 2 2 2 2 ...
 $ featureJE     : Factor w/ 2 levels NA,"Jerk": 1 1 1 1 1 1 1 1 2 2 ...
 $ featureMAG    : Factor w/ 2 levels NA,"Magnitude": 1 1 1 1 1 1 2 2 1 1 ...
 $ featuremeasure: Factor w/ 2 levels "mean","std": 1 1 1 2 2 2 1 2 1 1 ...
 $ featureaxis   : Factor w/ 4 levels NA,"X","Y","Z": 2 3 4 2 3 4 1 1 2 3 ...
 $ count         : int  50 50 50 50 50 50 50 50 50 50 ...
 $ average       : num  -0.0166 -0.0645 0.1487 -0.8735 -0.9511 ...
 - attr(*, "sorted")= chr  "subject" "activityname" "featureTF" "featureBG" ...
 - attr(*, ".internal.selfref")=<externalptr>

## first five rows of the dataset 

subject activityname featureTF featureBG featureAG featureJE featureMAG featuremeasure featureaxis count     average
1:       1       LAYING      Time        NA Gyroscope        NA         NA           mean           X    50 -0.01655309
2:       1       LAYING      Time        NA Gyroscope        NA         NA           mean           Y    50 -0.06448612
3:       1       LAYING      Time        NA Gyroscope        NA         NA           mean           Z    50  0.14868944
4:       1       LAYING      Time        NA Gyroscope        NA         NA            std           X    50 -0.87354387
5:       1       LAYING      Time        NA Gyroscope        NA         NA            std           Y    50 -0.95109044
6:       1       LAYING      Time        NA Gyroscope        NA         NA            std           Z    50 -0.90828466












