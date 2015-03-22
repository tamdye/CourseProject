# CourseProject
course project for Data Cleaning Class

this is the readme

I was able to follow the README in the directory that explained what the analysis files did.


In order to process the data, I completed 5 steps.

Step 1:  Combine the test and training data sets.
  First, I made a file of the training data called totalTrainData that column-combined the 'x_train.txt', 'y_train.txt', and        'subject_train.txt' data files.  It was 563 columns by 7,352 rows.
  Next, I made a file of the test data called totalTestData that column-combined the 'x_test.txt', 'y_test.txt', and                'subject_test.txt' data files.  It was 563 columns by 2,947 rows.
  Finally, I made a file of all of the data called totalData that was a row-combine of the training and test files.
  
Step 2:  Extract only the columns with mean and standard deviation
  First, I downloaded all of the column names for the variables that appear in the training and test data sets.
  Next, I created a file of the column numbers I wanted to keep, called Cols, by extracting the column numbers for every            variable that contained "mean" or "std" in its title.
  Finally, I made a file called extractTotalData that was a subset of TotalData created by keeping the column numbers from
    Cols.

Step 3:  Rename the activities with their descriptive names


Step 4:  Rename the variables with desciptive, tidy names
  Lower camel case
  dataLabels.csv
  library(reshape2) and melt function
  
Step 5:  Summarize the data to find the average of each variable by subject and activity

  library(dplyr) and group_by and summarize functions
  summary choices you made
