---
Contributors:
- Lex Vogels
- Floris van Berloo
- Kay van der Linden
- Thomas Gadellaa
- Mehmet Eren Erdoğan
---

# Investigating the predictors of IMDb Ratings for Movies & Series
 
## Project Description

In the current digital era of entertainment, where rating systems have a significant impact, it is crucial to understand which factors might influence these ratings. It is clear that external factors such as viewer's satisfaction, perceived quality of the title (movie or tv series), and the place of watching the title might all affect the rating given by the viewer. However, from the perspective of creators, it might be way more interesting to look at factors that can internally be decided. What is the influence of certain actors on title ratings? Which genres tend to be rated higher? And does the consumer enjoy longer or shorter titles? 

The current research aims to deliver useful insights for content makers about which factors actually influence ratings and whether there are differences between the way in which movies are rated versus tv series. 

## Data Availability and Provenance Statements

The project benefits from open-source data that's available on https://datasets.imdbws.com. The available data is presented by IMDb, which is an organisation that is independent from the creators of the movies and tv series we are researching. Furthermore, IMDb is one of the most popular platforms for rating movies worldwide. Due to these factors, the information extracted from IMDb can be considered relatively trustworthy. Furthermore, a dataset that was previously created using information from https://www.the-numbers.com/ will be used to measure "Star power" of actors. Since this information is also available to the public, we can use it for our research. The dataset has been downloaded from a dropbox link that can be shared/used by future researchers.

### Summary of Availability

All used data sources are publicly available on *IMDb Developer* and *the-numbers* (dropbox).
Due to this, the research can easily be replicated and extended during future research projects on IMDb ratings and which variables affect a rating of a movie and/or tv series. 

### Details on each Data Source
Analysing and predicting movies & tv series ratings, we use four seperate datasets that will be prepared and merged, such that an analysis can be done on one final dataset. The four datasets are listed below, including details on which variables are visible in the dataset and which variables we believe are valuable to our research. Therefore, this also elaborates on some of the cleaning process.

1. **Title basics**
  From the Title basics dataset we use numerous columns; either as independent variable, moderator, or control variable. Firstly, *Runtime* and *Genres* will be used as two of our independent variables in our research. Additionally, *Title Type* will function as a moderator (*movies* vs. *tv series*). Finally, we are using the year the title was launched as a control variable, because, for example, titles published longer ago have generally received more reviews from so-called "laggards" (late adopters), which might result in lower average ratings than titles that have been published very recently.
2. **Title ratings**
  The Title ratings dataset forms the basis for our dependent variable *Average Rating*, while *Number of Votes* can and will be used as a threshhold for movies & series we consider in our analysis.
3. **Name basics**
  From the Name basics dataset we will extract which actors/actresses are linked to which movie and/or tv series titles. In this way, we can analyse the effect of these people on the rating of a title. Therefore, the actor/actress will be one of the independent variables.
4. **Star power**
  This dataset will be used to compute the average ranking of all the ranked actors in the movie/series. Additionally, we will create a dummy variable for whether actors are considered "super stars".

## Dataset list and variable structure of final dataset

1. title_basics.tsv
2. title_ratings.tsv
3. name_basics.tsv
4. starPower.csv 

## Running the code
To run the code, follow these instructions:
1. Fork this repository
2. Open your command line / terminal and run the following code:
```
git clone https://github.com/{your username}/team-project-team_8
```
3. Set your working directory to `team-project-team_8` and run the following command:
```
make
```
4. In our repository, make is structured as follows:

a. Firstly, there are three makefiles. The makefile in the root repository starts data-preparation, and analysis.

![Makefiles](src/paper/makefile_structure.jpg)

b. The data-preparation makefile follows the following structure, ensuring that everything is cleaned and merged properly step-by-step:

![Data preparation structure](src/paper/dataprep_structure.jpg)

c. Finally, analysis is done according to the structure below:

![Analysis structure](src/paper/analysis_structure.jpg)

5. To clean the data of all raw and data files created during the process, run the following code in the command line / terminal: 
```
make clean
```
