# Multiple Linear Regression Model for King County

![awesome](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/Screen%20Shot%202020-12-22%20at%2012.35.15%20PM.png)

## Introduction 

For this project, we're given real estate data from King County. Our job is to create and solve a business problem using a linear regression model. We have total freedom in who our stakeholders are, and what the business problem is. For this project, we'll be using CRoss-Industry Standard Process for Data Mining (CRISP-DM) as our Data Science Process.

## Business Understanding

Our project will cater to first time home buyers, generally in their 20's and 30's and perhaps thinking of starting a family. Our regression model will help inform home buyers on which features most impact the overall price, so they can be more strategic when buying their first home. Our hope is to showcase what features may add additional costs, so buyers can reflect whether each feature is worth it or not.  

## Data Understanding 

Our original dataset contains real estate info for houses in 2014-2015, with features including square footage of lot and living, number of bedrooms and bathrooms, grade and condition, whether it's in the waterfront or not, just to name a few. The dataframe contains 21,597 pieces of data, giving us plenty to work with. 

Given that we are catering to first time home buyers, we've also added features not included in the dataset, including distance to points of interest (transportation centers, medical centers and police stations), distance to schools, school ratings, criminality rate and walking score. 

- <b>kingcounty.gov</b> Places of Interest & Criminality Data 
- <b>niche.com</b> School Ratings 
- <b>walkscore.com</b> Walk Score 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/df_hist.png?raw=true)

A histogram of our DataFrame shows which features follow a normal distribution, and it also gives us a great idea of which features we'd need to deal with as categorical. This knowledge will help us later when we process the data using log transformations and dummy variables. 

Features like distance and square footage (living and lot) have positively skewed distributions, signifying there are a number of properties that are a lot larger than the average home. Our outcome, price, also holds a positively skewed distribution, signifying a hefty set of homes that are priced much higher than the average. 

Our crime data and walk score, scraped data, lacked normality, decreasing the accuracy of our model. We binned the data in an effort to improve the accuracy of our model.

### Methods

Our original dataframe starts out with 21,597 pieces of data. We cleaned the data accordingly, taking out null values when necessary and dropping irrelevant columns. We then added additional data through web-scraping. Once our dataframe was complete, we performed log transformations, standardization and normalization techniques to get more accurate coefficients. We tested for multicollinearity in order to remove features that overlapped. Afterwards, we built our model, reflected on the results, and made adjustments accordingly. And repeat. 

### Results

After building 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/img1.png?raw=true)
![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/img2.png?raw=true)
![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/grade.png?raw=true)

Our added features seem to work out great as well. From the initial look, school rating seems to play a major role in pricing as well. Schools were rated on an A-F scale. We converted that scale into a numerical figure, with an A+ represented as a 1, A as a 2, A- as a 3 and so forth. Houses built around schools with an A+ tend to cost much higher than those at an A and A-. 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/grade_rank.png?raw=true)

Walk score had an interesting correlation with price as well. Based on our model, we found that walk scores with a bin between 70-89, meaning "Very Walkable" were priced higher. 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/walk_score.png?raw=true)

As expected, neighborhoods where crime rate is lower had homes with a high price range, and neighborhoods with a higher crime rate had homes that cost less. The model shows a negative correlation between price and total crime rate per capita. 


![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/Screen%20Shot%202020-12-22%20at%201.08.22%20PM.png?raw=true)

### Recommendations 

Based on our model, we would make the following recommednations to first time home owners: 
- Buy a home near a good school
- 


### Future Work 

For future work, we would do the following: 
- Calculate the school rating for the specific school closest to the home. 
- Include transit score and bike score from walkscore.com 
- Specify crime rate per capita using the specific home address instead of using zip code. This may have allowed for a more normal distribution. 

### Conclusion 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/total_crime.png?raw=true)

Our final model had an R-squared value of .702, an Omnibus of 271.631 and a Durbin-Watson score of 2.0. We feel confident that our final model can predict the home values, even outside of our dataset. 
