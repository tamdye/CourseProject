# CourseProject
course project for Data Cleaning Class

In order for this code to run, the source data needs to be downloaded to the working directory and unzipped.  Additionally,
I created an interim file, dataLabels.csv, that aslo needs to be downloaded from this repo into the working directory.

In order to process the data, I completed 5 steps.

Step 1:  Combine the test and training data sets.

  First, I made a file of the training data called totalTrainData that column-combined the 'x_train.txt', 'y_train.txt', and      'subject_train.txt' data files.  It was 563 columns by 7,352 rows.  Next, I made a file of the test data called totalTestData   that column-combined the 'x_test.txt', 'y_test.txt', and 'subject_test.txt' data files.  It was 563 columns by 2,947 rows.      Finally, I made a file of all of the data called totalData that was a row-combine of the training and test files.  It was 563   columns by 10,299 rows.
  
Step 2:  Extract only the columns with mean and standard deviation.

  First, I downloaded all of the column names for the variables that appear in the training and test data sets.  Next, I created   a file of the column numbers I wanted to keep, called Cols, by extracting the column numbers for every variable that contained   "mean" or "std" in its title.  Finally, I made a file called extractTotalData that was a subset of TotalData created by         keeping the column numbers from Cols.

Step 3:  Rename the activities with their descriptive names.

  At this point the extractTotalData file only contained the numbers 1 through 6 in the activity column.  I wanted to replace
  those numbers with the activity labels from the file 'activity_labels.txt'.  I merged the extractTotalData with the             activityLabels, matching the activity numbers in both files and appending a new column to extractTotalData with the             activity labels in it.  I then reordered the columns to make the dataset show the subject in the first column, the
  activity label in the second column and the remaining data in the following columns.

Step 4:  Rename the variables with desciptive names.

  I wanted all of my variables to be labeled with tidier names.  The original 'features.txt' file had some inconsistencies and
  typos.  The variables also contained dashes and parenthesis which are difficult to deal with in programs.  I transformed the
  data labels by hand in excel.  I made a file called dataLabels that included the original row number from 'x_train.txt' and
  'x_test.txt' files, the original column name from 'features.txt', and a new column that I input by hand called tidylabels.      All of the tidylabels use 'lower camel case' which is an R standard way of naming variables.  All inconsistences and typos      were corrected and all dashes and parenthesis removed.  I then saved the excel file in a CSV format in the file                 'dataLabels.csv' and put it in my working directory (a copy is included in this repo).  Then I used the tidylabels column of    the CSV file to create a new variable called tidyLabels and used that to create column names for reorderedData.  Finally, I     created a long, tall tidy dataset called FinalData by calling the library(reshape2) and using the melt() function to transorm   the prior column names into a variable.

Step 5:  Summarize the data to find the average of each variable by subject and activity.

  I called the library(dplyr) and used the group_by() function to summarize FinalData into a long, tall tidy data set that is
  grouped by subject, activity, and variable.  Then I used the summarize() function to summarize all of the measures to the
  mean of that measure.  Finally, I used the write() function to output the final tidy text file.
