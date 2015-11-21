---
title       : Check-In and Review Count for Restaurant Business
subtitle    : Capstone Project 
author      : Koh M.H.
job         : Analyst
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Background of this analysis

With the wide adoption of social media, published data is now easily available to consumers. For each business, the awareness and popularity of the business may be represented by the number of check-in clocked. This may be even more so for restaurant business. Amongst many attributes of the restaurant business, number of review counts received by the restaurants may have implication on the number of check-in clocked. This is a summary of the analysis about how the number of review counts received were related to the number of check-in for restaurants using linear regression methods (single and multivariate).

--- .class #id 

## Data Preparation and Exploration

The datasource for this analysis : "check in" and "business" files are from [Yelp Database](http://www.yelp.com/dataset_challenge). 
Below is a summary on data preparation :

* check-in file - 'checkin_info' data was transformed to total number of check-in (refer as 'sum').
* as at least 80% of business records had 'sum' data < 500 although the maximum of the full range was 14203. This analysis only focused on business records with sum < 500. 
* business file - for records with 'open' = TRUE, the 'hours' data was transformed to total number of business hours (refer as 'bizhrtotal').
* To smoothen out the spread of the 'stars', the records were transformed from 9 types of stars ratings to 3 rating levels (refer as 'rate') instead, namely 'H', 'M' and 'L'.
* Only business records with complete data (no 'NA') were considered for further analysis.

Result of basic exploratory analysis : number of review counts received is positively related to the number of check-in for restaurants. 

--- .class #id 

## Methods/Results and Discussion

Simple linear regression : to analyse relationship between check-in and review count.  

Observations : an increase in review count would result in an increase of 1.73 number of check-in. 
This model explained 52.66% of the variance (R squared=0.5266). With a p-value <=0.05, we could reject the H0 and thus claim that there was a postive relationship between check-in and review count.

Multivariate Step regression(backward) : to analyse possibility of confounding variables which might influence the relationship between check-in and review count.  

Observations : an increase in review count would result in an increase of 1.62 number of check-in.
This model explained 66.62% of the variance(R squared=0.6662).

Validation through testing data sets and examination of the diagnosis plot showed results were supportive of the positive relationship between check-in and review count.

--- .class #id 

## Conclusion

The analysis showed that there was a positive relationship between review count and number of check-in for restaurant business. When there were more review counts received, there were more check-in clocked. Thus business owners who are interested to improve publicity of their restaurants can consider putting efforts in attracting and encouraging customers, especially those who have positive experiences when they visited the restaurants, to provide reviews for their restaurants.

This is the end of the presentation.

Thank you.
