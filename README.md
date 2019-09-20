
# Module 1 Final Project: Flip or Flop
### Bryan Jamieson


## My Approach

This exploritory data analysis of Kings County Housing Data is intended for house flippers, trying to get the most bang for their buck. With house flippers in mind, I was interested to see if there was a relationship between houses price, house age, and zipcode. To figure this out, I used various data analysis and vizualisation techniques to understand the type of relationship between house price, house age, and zipcode.

First we will explore and understand the data. Next clean & Visualize The Data. Then Finally Model our data.



## Objectives

1) Explore and understand the data
   - Look at trends, extreme, null and missing values.
   - Added column to Data Set called "house_age"
   
2) Clean & Visualize The Data 
   - Before looking at my main variables: zipcodes, price, and house age,
     I am going to clean my data by dealing with the missing values
   - I see outliers, which I am going to tackle later on.
   - I am going to look at the missing values again and then replace them.
 
3) Modeling
   - sklearn modeling
   - splitting dataset into train and test sets
   - statsmodeling
   - OLS


## The Dataset

The Kings County Housing Data Set is named "kc_house_data.csv". 

## Column Names and descriptions for Kings County Data Set

id - unique identified for a house
dateDate - house was sold
pricePrice -  is prediction target
bedroomsNumber -  of Bedrooms/House
bathroomsNumber -  of bathrooms/bedrooms
sqft_livingsquare -  footage of the home
sqft_lotsquare -  footage of the lot
floorsTotal -  floors (levels) in house
waterfront - House which has a view to a waterfront
view - Has been viewed
condition - How good the condition is ( Overall )
grade - overall grade given to the housing unit, based on King County grading system
sqft_above - square footage of house apart from basement
sqft_basement - square footage of the basement
yr_built - Built Year
yr_renovated - Year when house was renovated
zipcode - zip
lat - Latitude coordinate
long - Longitude coordinate
sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

1.) Explore & Understand The Data
a)
* First we look for trends, extreme, null and missing values
* Then we added a new column to Data Set called "house_age"

* Explored column names and index ranges to see if there are missing values in the dataset.
* Also noted the type of data: integer, float, or object. 

* I realized there were missing values were in "waterfront", "view", and "year renovated",
  so I double checked this using "isna()" 

Result
* Both outputs above pointed out the same number of missing values in the dataset.

b)
* Created new variable "house_age" and added it to our dataset.


2.) Clean & Visualize Dataset
a)
* Before looking at my main variables: zipcodes, price, and house age,
  I cleaned my data by dealing with the missing values
* I saw outliers, which I tackled later on.
* I looked at the missing values again and then replace them.

b)
* Next, I copied the kc_df to look at the data - (called "newkc_df")

* I then removed the objects ('date', 'sqft_basement') and 'id' column,
  because that data was not neccessary for what I was looking at.

c)
* Then I checked to see what the column variables look like based on price by graphing a scatter plot

Result:
I had more data to clean

d)
* I then filled na values using isna().sum()
* After missing values were filled, I used IQR to remove outliers in dataset

* Now I wan't to visualize the data and graph it with a bar graph.
* Here we are trying to see the average house price for every house age (1, 2, 3, 4 (years old), etc.) 

Question: Which zip codes can I get the best bang for my buck when purchasing a house?
* This graph shows that houses 76 years old have the lowest average price of around 290k.
* This is the only average price based on house age under 300k. That's a good start.



Next I want to look at zipcodes!

Question: Which zipcodes have the highest average house prices?
* Looking at how price effects zipcode

Result:
* The boxplot told us that zipcode 98039 has the highest average house prices!


I ran the same model, but this time, to look at how house age effects zipcode

Question: Which zip codes have the oldest houses that I could renovate?
* Looking at how house_age effects zipcode

Result:
* 98102 Zipcode average house age is between 90-95 years old. Yet, on average, the house prices range from 50k-100k.


Lastly, I ran a pairplot to view interesting variables to use in my model.
* I used ('price','house_age','zipcode','sqft_living','bedrooms') in this pairplot.


## 3.) Modeling

# I modeled the data using two methods

1) sklearn modeling
   * splitting dataset into train and test sets
2) statsmodeling
   * OLS
   
Results:
For both models, I used the same x variables ('house_age','zipcode','sqft_living','bedrooms'). I got a higher r2 value with sklearn modeling compared to statsmodeling. 
* (sklearn modeling) r2 value = (.55)
* (statsmodeling( r2 value = (.54)

Both r2 values show the relationship is moderately strong and we did a good job!
Also, the p values are 0 in both models. I tried using the same linear regression equation for just one or two x variables and got horrible r2 results (0.03,0.04). I left the bad r2 results in there because this project is exploritory!

