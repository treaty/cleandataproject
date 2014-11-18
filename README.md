cleandataproject
================
### how the run_analysis.R works ? 

## First, it will download the file from the desired website and unzip the download file in the working dictionary, the unziped file is called UCI HAR Dataset.  
   these are the commands: 
   download.file("https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip","./ori.zip",method="curl")
   unzip("ori.zip")
## Second, it will read the data into R then merges the training and the test sets to create one data set and named the variables 
   these are the commands:
   testx<- read.table("UCI HAR Dataset/test/X_test.txt")
   testy<- read.table("UCI HAR Dataset/test/y_test.txt")
   testsub<- read.table("UCI HAR Dataset/test/subject_test.txt")
   trainx<- read.table("UCI HAR Dataset/train/X_train.txt")
   trainy<- read.table("UCI HAR Dataset/train/y_train.txt")
   trainsub<- read.table("UCI HAR Dataset/train/subject_train.txt")
   datx<- rbind(testx,trainx)
   daty<- rbind(testy,trainy)
   names(daty)<-c("activity")
   datsub<- rbind(testsub,trainsub)
   names(datsub)<-c("subject")
   datall<- cbind(datx,daty,datsub)
   feature1<- read.table("UCI HAR Dataset/features.txt")
   feature2<-t(feature1)
   feature3<-feature2[2,]
   names(datall)<-c(feature3,"activity","subject")
## Third, it will extracts only the measurements on the mean and standard deviation for each measurement 
   these are the commands:   
   dat2<-datall[,grepl("mean\\()|std\\()",names(datall))]
   dat3<-datall$activity
   dat4<-datall$subject
   datsel<-datsel<-cbind(dat2,activity=dat3,subject=dat4)
## Fourth, it will change to apply descriptive activity names to name the activities in the data set 
   these are the commands:
   datsel<-datsel<-cbind(dat2,activity=dat3,subject=dat4)
   labname<- read.table("UCI HAR Dataset/activity_labels.txt")
   names(labname)<-c("activity","activityname")
   datsel2<-merge(datsel,labname,by="activity") 
## Fifth, it will first melt the the dataset into a tall and narrow format and then separate the each variable from one column to multiply columns and then labels with the descriptive variable names 
   these are the commands: 
   library(reshape2)
   library(tidyr)
   library(dplyr)
   library(data.table)
   datmelt<-melt(datsel2,id=c("subject","activity","activityname"),variable.name="variable")
   y<- matrix(1:2, nrow = 2)
   x <- matrix(c(grepl("^t",datmelt$variable),grepl("^f",datmelt$variable)),ncol=2)
   datmelt$featureTF<-factor(x %*% y, labels = c("Time", "Frequency"))
   x <- matrix(c(grepl("Acc",datmelt$variable), grepl("Gyro",datmelt$variable)), ncol = 2)
   datmelt$featureAG<-factor(x %*% y, labels = c("Accelerometer", "Gyroscope"))
   x <- matrix(c(grepl("BodyAcc",datmelt$variable), grepl("GravityAcc",datmelt$variable)), ncol = 2)
   datmelt$featureBG<-factor(x %*% y, labels = c(NA,"Body","Gravity"))
   x <- matrix(c(grepl("mean()",datmelt$variable), grepl("std()",datmelt$variable)), ncol = 2)
   datmelt$featuremeasure<-factor(x %*% y, labels = c("mean","std"))
   datmelt$featureJE<-factor(grepl("Jerk",datmelt$variable), labels = c(NA,"Jerk"))
   datmelt$featureMAG<-factor(grepl("Mag",datmelt$variable), labels = c(NA,"Magnitude"))
   x <- matrix(c(grepl("-X",datmelt$variable),grepl("-Y",datmelt$variable),grepl("-Z",datmelt$variable)),ncol=3)
   datmelt$featureaxis<-factor(x %*% y, labels = c(NA,"X","Y","Z"))
   datsum<-select(datmelt,subject,activityname,featureTF,featureAG,featureBG,featuremeasure,featureJE, featureMAG,featureaxis,value)
## Finally, it will creates an independent tidy data set with the average of each variable for each activity and each subject and write the data set to the file called "dat.txt" in the directory. 
   these are the commands: 
   datsum2<-data.table(datsum)
   setkey(datsum2,subject,activityname,featureTF,featureBG,featureAG,featureJE,featureMAG,featuremeasure,featureaxis)
   datframe<-datsum2[,list(count=.N,average=mean(value)),by=key(datsum2)]
   write.table(datframe,"dat.txt",row.names=F)
## In summary, using run_analysis.R one can use the original download zip file called "ori.zip" to generate the tidy data set directly called "dat.txt". For more informaition about the meaning of each variable, one can find in the Codebook file codebook.md. 

