# Impressions-as-a-function-of-spend-duration-country

# miniproject2 - Impressions as a function of spend, duration, and country

I chose to look at the Snapchat election advertising data. Although I actually deleted my Snapchat and do not generally view it as a news source, I thought it would be interesting to look at election advertising given the excitement of the primaries. I decided to look at the 2020 data since it would be the newest and most relevant

I decided to investigate what factors influence the number of impressions and how much each factor affects impressions. The goal of any marketing campaign is first and foremost to have consumers buy, or people vote, but people need to see the ads to know about the opportunity. Given the data set, I only had a few numerical options that I could look at, so I chose spend, duration and country. For spend, how closely correlated are money and number of impressions? I assumed that there would be a strong correlation because more spending yould mean that Snapchat displays the ad more.  For duration, I wanted to see how the duration affected the number of impressions: would it be linear or would there be a drop off after the ad had been playing for a long time? I assumed that overall, a longer duration means more time for ads to be seen and therefore more impressions. Finally, I was curious to see how different countries spent money on ads, particularly since this data was focused on election advertising data.

I chose to make a simple linear regression comparing spend with impressions. I also 

#### Steps to analyze data:
1. First I needed to synthesize the data
2. Spearated dates and times for both start and end dates in different columns (Data, text to columns, delimited)
3. The end date column has several empty cells so I treated those as present day and filled in 2/27/20
4. To look at countries, I assigned each of the 12 countries a number so that I could perform a linear regression analaysis.

##### Impact of Spend on Impressions

First I conducted a single variable linear regression to look at the impact of spend on impressions. I assumed that more money spent likely meant more impressions. 

I ran a linear regression and came up with the equation: impressions = 397.11xspend+97,755
This would mean that a $400 increase in spend would lead to a corresponding $158,800 increase in impressions, leading to total 158,800 impressions.

The R^2 value is 0.58 which means that only about 58% of the relationship between soend and impressions can be explained by a linear relationship. THe p-value of the intercept is 0.162, well about teh standard accepted 0.05, which would further indicate a lack of relationship and that further analysis is needed. There is also a large standard error, the average distance from data to the best fitted line is $10. Additionally, the F significance is 1.38 x 10^-197 which means that the null hypothesis of both coefficients being zero is likely not true and thus there must be at least some validity to this model.

Overall, spend is not a great predictor of impressions, soit is important to evaluate other data.

![](https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/Impressions%20by%20Spend.png)

##### Multi Variable Regression - spend, duration and country



##### Multi Variable Regression - spend and country only


#### Not a Linear Regression - but still interesting insight

![](https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/Impressions%20by%20Spend.png)

![](https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/Total%20Impressions%20by%20Country.png)

Data set was obtained from https://www.snap.com/en-US/political-ads/. <Snapchat Political Ads Library>

Excel data can be found:  <Github>
