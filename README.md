# Multiple Linear Regression Model for King County

![awesome](https://www.racialequityalliance.org/wp-content/uploads/2016/10/assessors_social-1.jpg)

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

We find the following features to have a strong linear relationship with price: square foootage (living, above) and building grade. 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/img1.png?raw=true)
![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/img2.png?raw=true)
![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/grade.png?raw=true)

Our added features seem to work out great as well. From the initial look, school rating seems to play a major role in pricing as well. Houses built around schools with higher ratings tend to cost more. 

![alt text](https://github.com/Eric-G-Romano/dsc-phase-2-project/blob/christian_branch/grade_rank.png?raw=true)

### Conclusion 

After multiple iterations, our final model had an R-squared value of ____. 

### Recommendations 

Based on our model, we would make the following recommednations to first time home owners: 
- Buy a home near a good school
- 

### Future Work 

- Look into bike score and transit score for each city 
- Calculate walk score based on address instead of zip code 
