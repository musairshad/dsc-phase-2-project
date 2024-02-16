# Popcorn Time!!! Fortune Movie Productions getting ready to entertain you
<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/BoxOffice_picture.jpg" width="612" height="408"
</p>


## Business Problem

Fortune Movie Productions have decided to make their First Movie studio, and exploring what types of films are currently best at Box Office. We aim to evaluate which movie genres are faster reach to Audience, what type of movies makes best revenue, and who are the best directors/writers/actor whose movie hit Box Office.

**Goals:**

   - *Popular Movie Genres are top ones in today's movie industry*
   - *Which movie genre makes good revenue domestically and worldwide*
   - *Production Budget, Director & Actor recommendations for Top Genres*
   - *Best Release day*


## Dataset:

We are using movie datasets for our analysis from:

* [Box Office Mojo](https://www.boxofficemojo.com/)
* [IMDB](https://www.imdb.com/)
* [Rotten Tomatoes](https://www.rottentomatoes.com/)
* [TheMovieDB](https://www.themoviedb.org/)
* [The Numbers](https://www.the-numbers.com/)

Dataset Box Office has columns title, studio, domestic_gross, foreign_gross & year. IMDB database has 8 tables, each table with 2-8 columns each. This database was used to explore principals in movie industry. Database Rotten Tomatoes has 2 datasets. Dataset rt_movie has id, synopsis, rating, genre, director, writer... This source was not used for our analysis since this dataset has more missing values and columns was not useful. Dataset TheMovieDB has columns genre_ids, id, ori_lang, ori_title, popularity, release date, title, vote_av, vote_ct. Dataset TheNumbers has columns id, release_date, movie, production_budget, domestic_gross, worldwide_gross.

We used IMDB database which has 8 Tables, 3 of the tables had necessary columns such as Genres, NumVotes, AverageRating ... for analysis. Similarly, Dataset TheMovieDB & TheNumbers were used to find which genre made Box office hit, and collected high revenue domestically & worldwide. 

For additional info regarding genre names and their corresponding numbers used in TheMovieDB Dataset for Data Cleaning, following source was used:
https://www.themoviedb.org/talk/5daf6eb0ae36680011d7e6ee >

## Dataset Evaluation & Visualization:

**Tableau Dashboard:** https://public.tableau.com/app/profile/yamuna.umapathy/viz/FortuneMovieProject1/Dashboard1 
<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Tableau.png" width="600" height="617"
</p>

**Top Genres:** 
We were filtering the dataset with mean `vote_average`, TheMovieDB Dataset was used for visualizing top 10 genres based on their `vote_average` and `genre_list`. Analysis shows Animation, Romance, Drama and Science Fiction was the trending genres with highest ratings.

<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Bargraph1.png  " width="750" height="559"
</p>

Based on above analysis, we were analyzing top 4 genre categories with `genre_list` and `vote_average` standings using Boxplot.

<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Bargraph1.png" width="750" height="568"
  
</p>

Above Boxplot visualization shows Animation has best ratings. Romance & Drama has similar ratings. 

**Top 4 Genre Vs Production Budget**
Using SQL database table movie_basics with top 4 genres, and merging with dataset tn_moviesbudget to have columns genre, production_budget, gross avenue together. Merging the data using movie title as primary key. Visualizing which genre makes best revenue.

<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Bargraph2_budget.png" width="750" height="518"
</p>

Above visualization shows production budget for Animation starting at 70M+, Scifi budget is 35M+. Other options to make top movies in low budget would be Romance & Drama which starts at 20-25M. 

**Revenue:**: Next, we want to analyze which genres makes the most revenue, which is one of the important factor to decide. We are using the 
same dataset tn_movies_moviebasics, and analyzing between top genres and domestic_gross. 

<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Bargraph3_Revenue.png" width="750" height="496"
</p>

Above visualization shows Gross revenue increase in Animation and Scifi. Animation earns 10-15% profit where as Sci-Fi earns 50-70% profit. Gross revenue for Romance and Drama was not appealing.

**Directors for Animaion:** We are looking to find Top Actors & directors for Animation and Sci-Fi since they have the better revenue turnover than Romance & Drama. Filtering movie_basics with averagerating> 7 and joining table principals & table persons for famous movie directors & actors with best rating & total number of movies they have done. Visualizing Directors in USA with rating > 7 for Animation.

<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Linegraph_animation.png" width="750" height="583"
</p>

Above Visualization shows Don Hall, Rich Moore, Stephen Anderson, Chris Mackay & Phil Johnston are top 5 directors with best ratings and 
who made more movies for Animation. 

**Actors for Animation**: Filtering Sql database with average rating greater than 7 for Best Actors for Animation. Here, we are joining Tables movie_basics, movie_ratings, movie_akas, principals and persons to filter data who are Best Actors for Animation. 

<p align="center">
 <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Actorslist.png" width = "750", height = "232"
</p>

Above Visualization shows Anthon Baker, Aleksandr Bible, Mahershala Ali, Ryo Narita & Jason Boarswain are top Actors for Animation with best ratings. 

**Directors for Sci-Fi:** Similarly,  Filtering movie_basics with rating greater than 7 and joining table principals & table persons for famous movie directors & actors with best rating & total number of movies they have done. Visualizing Directors in USA with rating > 7 for Sci-Fi.

<p align="center">
    <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Linegraph_scifi.png" width="750" height="579"
</p>

Above Visualization shows Joe Russon, Anthony Russo, Ryan Knight, Timothy Thomas & Felix Catala are top 5 directors with best ratings and 
who made more movies for Sci-Fi.

**Actors for Sci-Fi**: Similarly, Filtering Sql database with average rating greater than 7 for Best Actors for Sci-Fi. Here, we are joining Tables movie_basics, movie_ratings, movie_akas, principals and persons to filter data who are Best Actors for Sci-Fi. 
<p align="center">
 <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Actorslist.png" width = "750", height = "232"
</p>

Above Visualization shows Alison Kam, Mitchell Campos, Victoria Holt, Jason Peter Kennedy and Heath Carr are top Actors for Sci-Fi with best ratings. 

**Release Day:** Finally, we want to see what day of the week works best for movie release and earns best revenue. We are using TheMovieDB dataset, and visualizing `popularity` vs `release_day`. Analysis shows FRIDAY is the best day which earns highest revenue in movie industry. 

<p align="center">
  <img src = "https://github.com/YamunaU75/FortuneMoviePhase2/blob/main/images/Releaseday_scatter.png" width="750" height="522"
</p>

## Conclusion & Recommendations:

**Genres:** Based on our analysis, top genres are Animation, Sci-Fi and Drama.

**Revenue:** Animation 10-15% revenue increase, Sci-Fi has 50-70% revenue increase, Drama has no gain & no loss.

**Production Budget:** Considering budget 70+ million for Animation, and 35+M for Sci-Fi.

**Directors & Actors:** Sorted Best Directors & Actors based on ratings for Animation & Sci-Fi.

**Release Day:** Friday is recommended to be best day for release day, earns more revenue in the movie industry.

## Next Steps:

- *Utilize Awards database for best directors across genres.
- *Explore TV-shows and international movies for industry trends.
- *Consider advertisement data for informed decision-making.
- *Incorporate findings to improve entry into movie production industry.


## Repository Structure

```
├── Images
├── zippedData
├── .gitignore
├── presentation
├── README.md
└── index.ipynb
```
