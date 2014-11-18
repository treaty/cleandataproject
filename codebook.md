Codebook
================
##describing the variables

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

subject                 activityname      featureTF      featureBG            featureAG    featureJE  
 Min.   : 1.0   LAYING            :1980   Time     :7200   NA     :4680   Accelerometer:7200   NA  :7200  
 1st Qu.: 8.0   SITTING           :1980   Frequency:4680   Body   :5760   Gyroscope    :4680   Jerk:4680  
 Median :15.5   STANDING          :1980                    Gravity:1440                                   
 Mean   :15.5   WALKING           :1980                                                                   
 3rd Qu.:23.0   WALKING_DOWNSTAIRS:1980                                                                   
 Max.   :30.0   WALKING_UPSTAIRS  :1980                                                                   
     featureMAG   featuremeasure featureaxis     count          average        
 NA       :8640   mean:5940      NA:3240     Min.   :36.00   Min.   :-0.99767  
 Magnitude:3240   std :5940      X :2880     1st Qu.:49.00   1st Qu.:-0.96205  
                                 Y :2880     Median :54.50   Median :-0.46989  
                                 Z :2880     Mean   :57.22   Mean   :-0.48436  
                                             3rd Qu.:63.25   3rd Qu.:-0.07836  
                                             Max.   :95.00   Max.   : 0.97451

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












