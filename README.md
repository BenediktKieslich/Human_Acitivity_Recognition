
The analysis.R script performs data cleaning and transformation on the UCI HAR Dataset to create a tidy dataset with the average of each variable for each activity and each subject. The script consists of several steps, each addressing a specific task:

Merging the Training and Test Sets:
The script reads the training set and test set data from the files train/X_train.txt and test/X_test.txt, respectively.
It combines the two datasets using the rbind() function, creating a merged dataset data_set.
The script displays the first 4 rows and 5 columns of the merged dataset.
Extracting Mean and Standard Deviation Measurements:
The script reads the feature names from the file features.txt using the read.table() function.
It assigns the feature names to the columns of data_set using colnames() function.
The script selects only the measurements on the mean and standard deviation for each measurement using the grepl() function and creates a subset of data_set.
The script displays the first 4 rows and 5 columns of the updated dataset.
Using Descriptive Activity Names:
The script reads the activity labels for the training set and test set from the files train/y_train.txt and test/y_test.txt using the read.table() function.
It combines the two sets of activity labels and maps them to descriptive activity names using a predefined vector labels.
The script adds an "Activity" column to data_set containing the descriptive activity names.
The script displays the first 4 rows and 5 columns of the updated dataset.
Appropriately Labeling the Data Set:
The script performs a series of string replacements on the column names of data_set using the gsub() function to make them more descriptive and consistent.
The script displays the updated column names and the first 4 rows and 5 columns of the dataset.
Creating a Second Tidy Data Set with Average Variables:
The script reads the subject IDs for the training set and test set from the files train/subject_train.txt and test/subject_test.txt using the read.table() function.
It combines the two sets of subject IDs and adds a "Subject" column to data_set.
The script displays the first 4 rows and 5 columns of the updated dataset.
Calculating the Average of Variables by Activity and Subject:
The script uses the dplyr library to group the data by Subject and Activity.
It calculates the average of each variable for each activity and each subject using the summarise_each() function.
The resulting dataset is stored in average_data_set.
Writing the Tidy Data Set to a File:
The script uses the write.table() function to save average_data_set as a text file named "tidy_data_set.txt" without row names.
Running the Script

To run the analysis.R script, follow these steps:

Set the working directory to the location where the script is located.
Ensure that the UCI HAR Dataset is present in the same directory as the script.
Open the script in an R environment or R script editor.
Execute the script line by line or run it all at once.
The resulting tidy dataset will be saved as "tidy_data_set.txt" in the working directory.