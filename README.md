# Successful Film Genres
By Jonathan Nunez

# Business Understanding
The company is looking into expanding into the box office market. The company sees the potential income in creating their own original video content through the use of their own new movie studio. I was tasked with exploring what types of films are currently doing the best at the box office. As the company is looking for the genre(s) that are doing the best, I plan to narrow this down by finding which genre(s) yields the highest return on investment on average.

# Data Understanding
The data being used to fulfill this task is the [IMDB](https://www.imdb.com/) movie database, [Box Office Mojo](https://www.boxofficemojo.com/), and [The Numbers](https://www.the-numbers.com/) datasets. The data in The Numbers contains movie records ranging as early as 1920 up to 2019, while the IMBD, and the Box Office Mojo data is more focused between 2010 through 2019. Among the three datasets, you can find information such the genre or genres the listed film falls under, the date the film was released, both domestic and foreign gross, to even the production budget of the film.

## Data Preparation
To prepare the data, I first replace the column names in both The Numbers and Box Office Mojo dataframes for consistency, and for easier data merging. From there I made sure the data in shared column names was uniform and correctly formatted. Both dataframes include domestic and foreign gross columns, but the formats varied, containing currency symbols or were of non-numeric data types. I created a function to clean and convert these values into integer data types. For films with similar titles in both dataframes, but different gross values, I averaged the numbers as I merged the data for greater accuracy.

Since combining data generated quite a few of NaN values, I created another function that would not only drop these values but also sort and reset the dataframe’s index. Some films in the data contain multi genres, and in order to get an accurate gross per genre I split multi-genre films and create new rows for each genre. This approach ensured accurate genre representation while maintaining original values in other columns. From there I divided the 'production_budget', 'domestic_gross', and 'foreign_gross' columns by the number of genres per unique film to get gross values per genre. To represent profit accurately, I used the return on investment (RoI) formula to get return percentages for domestic, foreign, and overall gross, providing a clearer gain of profit across genres over a 10 year span.

# Exploratory Data Analysis
### Domestic Return on Investment
The top 5 highest grossing genres in the domestic market are Animation, Sci-Fi, Adventure, Action, and Fantasy. When it comes to return on investment on the other hand, the top 5 genres are completely different than the highest grossing. **The highest returns on investment genres domestically are Mystery, Horror, Thriller, Documentary, and Romance.** While the highest grossing films may generate the most money, they seem to not generate a high return on investment like Mystery and Horror at almost at a **500% return.**
![Domestic Return](images/domestic_return.jpeg)

### Foreign Return on Investment
For the most part, the foreign RoI chart is very similar to the domestic results. For the foreign RoI, the top 5 genres are **Mystery, Horror, Thriller, Animation, and Sci-fi**. Just like the domestic RoI, mystery is the highest return with almost **800% return average**, and horror comes in second with a little under **750% average return**.
![Foreign Return](images/foreign_return.jpeg)

### Total Return on Investment
In the Total Return on Investment chart, the top 5 genres with highest average return are **Mystery, Horror, Thriller, Romance, and Sci-fi**. Just like the other two RoI charts, both mystery and horror are the top genres. Mystery overall return was nearly a **1400% return**, and horror at **1300% return**. Among the three RoI charts, the results were consistent, especially for the top 3 genres being **Mystery, Horror, and Thriller**.
![Total Return](images/total_return.jpeg)

# Conclusions
Through the analysis of this data, we are able to answer the following questions:

**What are the top genres recommended for creating a first film?**

The top 5 genres I would recommend the company look into for a possible first film would be **Mystery, Horror, Thriller, Romance, and Sci-fi, genres.** Overall these 5 genres appear to give the best return in a domestic as well as a foreign market if the company wants to release their film overseas.

**Which genre(s) has the highest return on investment?**

Overall, the one genre that had the highest return on investment is the **Mystery** genre. In the domestic market this genre averaged at nearly a **500% return**. In the foreign market, this genre RoI nearly doubled from a 500% return to an **800% return**.

**Are the top genres consistent throughout both domestic and foreign markets?**

For the most part, the top genres in the domestic and foreign markets are consistent with **Mystery, Horror, and Thriller** being the top three. Spots four and five would change between **Documentary, Romance, Sci-fi, and Animation** in the domestic and foreign markets. Ultimately **Romance, and Sci-fi** made it to the top 5 as overall these two genres had the highest return.

## Limitations
While in the end, these data sets do have over 1000 films in common, there was a lot of data that had to be dropped due to simply not having the genre(s) of the film, and by dropping these values there is a possibility of missing out on genres that did extremely well or very poorly that could have changed the outcome. 

Another limitation I found with the data was that some films have the same title, but are made by different studios in foreign countries, so any film(s) that happen to have the same title could have had their values, gross values specifically, changed leading to possible inaccuracies for genres value averages.

## Recommendations
The top 5 genres with the highest return on investment are **Mystery, Horror, Thriller, Romance, and Sci-fi**. Even though the list of genres has been narrowed down to 5 it doesn’t mean instant success in one of those genres. I recommend further research on the recommended genres, specifically on the films that fall under these genres that are considered successful. 

Also, the data sets used for this project included films from around the world. Depending on what the primary market the company's focus is on, I would recommend gathering data for that specific market and running the tests again as there is always the **possibility that a film will do well in one market but fail in a different market.**

## Next Steps
**Further analyzing the data could help in giving a better understanding of the success rate of a genre.** In this project the main focus was narrowing down the genres and this was done by finding the return on investment. Now that we have the top genres, the next steps would be to **narrow the dataset to these specific genres, and research the films listed in these genres.** Finding out what made these films successful or even failures.

With the data narrowed down to the top 5 genres, **we can get a better understanding of how a specific genre has done over a set period.** For example, throughout the data, the **mystery genre didn’t have the highest gross both domestic and foreign, but it did have the highest RoI overall.** Is this result because the genre is becoming popular over the years, or are there a few outlier films that just did very well overall and boosted this genre to the top?

The current data has films that were released between 2010 and 2019, by **running these same tests on data containing films from 2020 to 2025**, it could help in finding the current movie genre trend, and depending on the results of both tests it could help solidify the recommended genre(s).

## For More Information
Full data analysis in [Jupyter Notebook](successful_films_notebook.ipynb) or review the [presentation](Successful_Film_Genres_Presentation.pdf).

## Repository Structure
- images
- README.md
- [Successful_Film_Genres_Presentation](Successful_Film_Genres_Presentation.pdf)
- [successful_films_notebook](successful_films_notebook.ipynb)
