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

The R^2 value is 0.58 which means that only about 58% of the relationship between spend and impressions can be explained by a linear relationship. The p-value of the intercept is 0.162, well about the standard accepted 0.05, which would further indicate a lack of relationship and that further analysis is needed. There is also a large standard error, the average distance from data to the best fitted line is 10. Additionally, the F significance is 1.38 x 10^-197 which means that the null hypothesis of both coefficients being zero is likely not true and thus there must be at least some validity to this model.

Overall, spend is not a great predictor of impressions, so it is important to evaluate other data.

![](https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/Impressions%20by%20Spend.png)

##### Multi Variable Regression - spend, duration and country
I again performed the same steps listed above but instead of just spend and impressions, I chose to include days of duration and country to see their respective effects on impressions.

Immediately after I ran the regression I notices the large p-value of duration (.93). As a result, it was clear to me that duration would have no statistically significant impact on imppressions, so I elected to again run a multi variable regression to look only at spend and country in relation to impressions.

##### Multi Variable Regression - spend and country only
I ran the linear regression which resulted in the following equation: impressions = 397spend+17,533country+56,767. The standard error for spend is again 10.51 and the standard error for country is 17,533 which means that the average distance to the best fit line is 17,533. This is a significant error and indicated that It is worth noting that the results for any regressions using country may be skewed for the country variable because I randomly labeled each country with a number and the data set did not have any information regarding number of, or percentage of users in each country. As a result, it is not relevant to say that an increase of 1 in a country about have a effect because you would then just be talking about a different country.

The R^2 value is 0.58 again, so 58% of the relationship between spend and impressions as well as country and impressions can be explained by the best fit line. The earlier determined equation would mean that the effect of spend would be the same as in the first, single variable regression. The p-value for country is .455 which is above the accepted standard of 0.05, so the data is not statistically significant. the intercept p-value is also at 0.52, which is above the 0.05 threshold. Significance F is again very small, 2.99x10^-196, which indicated that there is some relationship between the three variables. This regression would indicate that most of the correlation is due to spend, rather than country.

#### Not a Linear Regression - but still an interesting insight

I was really interested in which countries have the most political ads and no surprise, the US had significantly more impressions than any other company (approximately 15x the next closest country). It is difficult to see which coutry is second from the first chart but when only comparing non-US countries, Australia is a clear standout. This mihgt be useful for candidates to see where they get the most traction and even business owners is this is a sample of a larger trend

![](https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/Total%20Impressions%20by%20Country.png)

![](https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/Impressions%20by%20non-US%20Country.png)

Overall, it was fascinating to see what factors most heavily influence impressions, an end goal for many media marketers. Spend has the highest correlation with 58% followed by country and then duration. However, given that none of these variables have a particularly high correlation to impressions, perhaps there are other variables that weren't included in the data or aren't possible to measure (for example how interesting an ad is) that would have a greater impact on the number of impressions.

Data set was obtained from https://www.snap.com/en-US/political-ads/. <Snapchat Political Ads Library>

Excel data can be found: https://github.com/kamccarren/Impressions-as-a-function-of-spend-duration-country/blob/master/McCarren%20Mini%20Project%202%20Final.xlsx <Github>
