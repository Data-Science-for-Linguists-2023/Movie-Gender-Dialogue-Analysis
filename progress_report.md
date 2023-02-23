# Progress Report

## Progress Report 02/10/2023
I initialized a git repo for my term project *Hollywood and Gender: A Quantitative Analysis of Movie Dialogues*. I laid out my project plan which summarizes the data, where they come from, and my initial plans for analysis. Placeholders for License information and a Readme were also created.

## 1st Progress Report 02/24/2023
I have created the four main data frames based on the data from the Cornell corpus. Many of the data frames have references to other data frames so I will have to join them for the data frames to be fully comprehensible. The jupyter notebook for that is [here](Data_Object_Creation.ipynb.)

Three of the four dfs had the error "invalid continuation type" which I was able to resolve by specifying the encoding as ISO-8859-1. Although my terminal indicated that most of the files were encoded with ASCII, the files are very long so the encoding issue may have been further in the file.

**Sharing plan:** I believe that the data are open licensed, but I will be reaching out to one of the contributors to make sure. They also specify that anyone working with the data notify them so they can keep track of who is using the data. My plan is to make everything open, depending on the copyright of the original data set. At the very least I will make my data easily cross-referenced to the original data set, using the same movie, character, and line IDs.

Until I find out the licensing for the data I have uploaded the first 5 lines of each data frame in to the [data_sample](data_sample/) directory.
