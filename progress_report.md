# Progress Report

## Progress Report 02/10/2023
I initialized a git repo for my term project *Hollywood and Gender: A Quantitative Analysis of Movie Dialogues*. I laid out my project plan which summarizes the data, where they come from, and my initial plans for analysis. Placeholders for License information and a Readme were also created.

## 1st Progress Report 02/24/2023
I have created the four main data frames based on the data from the Cornell corpus. Many of the data frames have references to other data frames so I will have to join them for the data frames to be fully comprehensible. The Jupyter Notebook for that is [here](Data_Object_Creation.ipynb).

Three of the four dfs had the error "invalid continuation type" which I was able to resolve by specifying the encoding as ISO-8859-1. Although my terminal indicated that most of the files were encoded with ASCII, the files are very long so the encoding issue may have been further in the file.

**Sharing plan:** I believe that the data are open licensed, but I will be reaching out to one of the contributors to make sure. They also specify that anyone working with the data notify them so they can keep track of who is using the data. My plan is to make everything open, depending on the copyright of the original data set. At the very least I will make my data easily cross-referenced to the original data set, using the same movie, character, and line IDs.

Until I find out the licensing for the data I have uploaded the first 5 lines of each data frame in to the [data_sample](data_sample/) directory.

## 2nd Progress Report 03/24/2023
### Found Data:
I confirmed with a contributor of the corpus that the data is able to be fully shared. I have added a [data folder](./data/) that has all the .txt files of the corpus.

### Licensing:
I have added the [Licensing information](./LICENSE.md) for my code and data output. I have made my code and any objects output from the code open for non-commercial use with attribution.

### Data Progress:
6020 characters were missing gender markers in the initial corpus. I utilized [NLTK's names corpus](https://www.nltk.org/howto/corpus.html#word-lists-and-lexicons) and was able to add 2229 gender markers for the characters in the `characters_df` object. Because some names were on both the male and female name list I added a tag "A" for ambiguous. One of the characters from the first movie in the corpus is named "Miss Perky" and turns out there are several characters with "Miss", "Mrs.", "Mr.", "Ms.", or "Sir" in their names. Additionally some unnamed characters are named "Man", "Woman", "Boy", or "Girl" with various descriptors. You can see the progress [here](./Characters_Notebook.ipynb).

My Jupyter Notebooks are new replacements. As I continued to work with adding gender markers in the `characters_df` I realized my work with each df may be cumbersome and hard to navigate. I have created new JNBs for each dataframe in the corpus. See notes above on work in the `characters_df`. In the `utterances_df` [notebook](./Utterances_Notebook.ipynb) I have added sentences and word tokens, sentence counts, token counts, and average sentence length columns to facilitate analysis on turn structure.

I need to scrub some of the metadata in the [`movies_df`](./Movies_Notebook.ipynb) to be able to work with release year.

The 'dialogue' column in the [`conversations_df`](./Conversations_Notebook.ipynb) is a list of movie lines/utterances that I need to expand to be able to easily load in the utterance information.

### Other Updates:
I updated my [README](./README.txt) to make navigating my repo easier and to provide better understanding of what my project is about.


## 3rd Progress Report 04/09/2023
### Created Data:
I created a [new folder](./new_data/) where I have made csv files of my data objects. The exception is the csv from the utterances notebook, the file was too large to upload to GitHub so I kept the code to generate the csv file but commented it out. Similarly, I am still working on how best to handle the conversations from the corpus so there is no csv file for this data.

### Data Progress:
The same four notebook are in EXISTING status from my second progress report. I have added an [Analysis Notebook](./Analysis_Notebook.ipynb) that brings in all the data objects to analyze the data to answer my research questions.

With Na-Rae's help I was able to work with the [Character Notebook](./Characters_Notebook.ipynb) to generate gender based on specific strings found in character names. This method, combined with using the NLTK names lists, I was able to add 3141 gender markers. One next step, although it is low priority, is to split the character name column, some characters have first and last names, and their first names may be able to be matched to a name in NLTK so I may be able to add more gender markers.

I met with Emma to discuss the [Conversations Notebook](./Conversations_Notebook.ipynb), I am not sure how crucial this data is to my overall analysis. It organizes the lines from the [Utterances Notebook](./Utterances_Notebook.ipynb) into distinct conversations, but I may not go into this fine-grained of analysis.

In the [Utterances Notebook](./Utterances_Notebook.ipynb) I added POS tags from NLTK to each utterance. I will look at several specific POS to see if there is any usage variation.

### Next Steps:
Continue analysis overall. Dive deeper into linguistic features, slice and dice to get different views, create some graphs to visualize the data. Look closer at tokens and sentences per movie decade to see how they change over time. Cursory glance looks like there are more differences by decade than at the total level, so that could be revealing.

Look into doing a linear regression on `movie_decade` and `sentence_count` or  `token_count` to see if there are consistent patterns over time.
