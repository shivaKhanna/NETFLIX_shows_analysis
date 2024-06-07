


# NETFLIX DATA ANALYSIS
In this analysis, we delve into the vast world of Netflix series and shows, exploring various facets such as directors, different types of ratings, and the distinction between series and movies. By conducting univariate and bivariate analyses, we aim to extract valuable insights and provide a comprehensive summary of the data.

## Data Overview:
The dataset comprises a collection of Netflix series and shows, encompassing information such as titles, directors, ratings, genres, and whether they are categorized as series or movies.

## Analysis Approach:

## 1.Director Analysis:

Identify the most prolific directors in the Netflix dataset.
Determine if certain directors have a higher average rating compared to others.
Explore the distribution of shows directed by each director.

## 2.Rating Analysis:

Examine the different types of ratings assigned to Netflix movies and shows 

## 3.Type Analysis (Series vs. Movie):

Differentiate between series and movies in the dataset.
Compare the average ratings of series and movies to determine if there is a preference for one over the other.

## 4. Country_wise analysis
comparing the different countries with respect to the number of shows or movies released, and also in correspondence to the time frame when they are released

# Univariate and Bivariate Analysis:

Univariate Analysis: Explore individual variables such as ratings distribution, director frequencies, and type distribution (series vs. movie).
Bivariate Analysis: Investigate relationships between pairs of variables, such as the correlation between different rating sources, the influence of directors on ratings, and the impact of series versus movie type on viewer ratings.

## codes/functions used
### reading data

df = pd.read_csv('netflix_titles.csv')
df.head()

df.info()

df.shape

### cleaing data

df.isnull().mean()*100
checking of percentage of mean values

df['director'] = df['director'].fillna('unknown')
assigning generic values to the null slots

### Univariate analysis
type_counts = df['type'].value_counts()
type_counts
sns.countplot(x = df['type'],width=0.5)

director_counts = df['director'].value_counts()
director_counts

country_counts = df['country'].value_counts()
country_counts

top_countries = country_counts.nlargest(5)
top_countries
sns.countplot(x  = df['country'], order = top_countries.index)

### bivariate analysis 

sns.countplot(x = df['country'], order = top_countries.index, hue = df['type'])

plt.figure(figsize=(15,5))
sns.countplot(x = df['country'], order = top_countries.index, hue =df['rating'] )


# Summary of Findings:

## Summary
* 69.78% of content on Netflix consists of movies, while 30.22% are TV shows.

* 'Rajiv Chilaka' has released the highest number of shows.

* A significant portion of Netflix shows originates from the USA and India.

* The highest number of shows was added in the year 2019.

* July and December stand out as the months when the highest number of shows are released.

* The most common ratings for shows on Netflix are 'TV-MA' and 'TV-14.'

* In the United States and India, movies are more popular than TV shows.

* In the United Kingdom, both movies and TV shows enjoy equal popularity.

* Conversely, in Japan, TV shows are more favored than movies.

* In the United States, most shows are rated 'TV-MA.'

* In India, the majority of shows have a 'TV-14' rating.

* The United Kingdom sees a prevalence of 'TV-MA' ratings.

* Finally, in Japan, the common rating for most shows is 'TV-14.


