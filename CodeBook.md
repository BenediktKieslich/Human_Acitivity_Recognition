---
title: "CodeBook"
author: "Benedikt Kieslich"
date: "2023-07-06"
output: html_document
---

Merging the training and test sets:
Variables:
data_dir: Directory path for the dataset.
Code:
The code reads the training set and test set files using read.table() function.
It combines the two datasets using rbind() function and assigns the result to data_set.
The code displays the first 4 rows and 5 columns of the merged dataset.
Extracting mean and standard deviation measurements:
Variables:
features_name: Names of the features/measurements.
Code:
The code reads the feature names from the "features.txt" file and selects the second column using read.table() function.
It assigns the feature names to the columns of data_set using colnames() function.
The code identifies the indices of features that contain "mean" or "std" using grepl() function.
It subsets data_set to include only the selected measures using subset() function.
The code displays the first 4 rows and 5 columns of the updated dataset.
Labeling the data set with descriptive variable names:
Code:
The code performs a series of string replacements using gsub() function to modify the column names of data_set.
These replacements change abbreviations, remove parentheses and hyphens, and make the names more descriptive.
The code displays the updated column names and the first 4 rows and 5 columns of the dataset.
Using descriptive activity names:
Variables:
activities_train: Activity labels for the training set.
activities_test: Activity labels for the test set.
labels: Descriptive labels for activities.
Code:
The code reads the activity labels for the training and test sets using read.table() function.
It combines the two sets of labels using rbind() function and selects the first column.
The code assigns descriptive labels to the activities based on the labels vector.
It adds an "Activity" column to data_set containing the activity labels.
The code displays the first 4 rows and 5 columns of the updated dataset.
Creating a second tidy data set with average variables:
Variables:
subjects_train: Subject IDs for the training set.
subjects_test: Subject IDs for the test set.
Code:
The code reads the subject IDs for the training and test sets using read.table() function.
It combines the two sets of subject IDs using rbind() function and selects the first column.
The code adds a "Subject" column to data_set containing the subject IDs.
It uses the dplyr library to group the data by Subject and Activity.
The code calculates the average of each variable for each activity and each subject using summarise_each() function.
The resulting dataset is stored in average_data_set.
The write.table() function is used to save average_data_set as a text file named "tidy_data_set.txt" without row names.
This code book summarizes the steps performed to clean and transform the UCI HAR Dataset, including merging the data, selecting specific measurements, labeling variables, using descriptive activity names, and creating a second tidy data set with average variables.