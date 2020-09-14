# Always Be Closing #
## Graduate Course: Quantitative Analysis for Business

This was a project from a course on Linear Regression (a supervised machine learning technique for quantitative analysis). Below is the prompt from the client:

> My name is Jim Armilay, and I am a real estate broker in the state of Virginia. I have been moderately successful in the past five years selling large high-end homes, but recently more rival brokers have been moving into this market. I think one way I can gain an advantage in this market is if I start to use data to study the home prices, but I'm not sure how to start. I recorded some of my recent sales with the Price in dollars and Square feet (Sqft) for each of the sales. The data is included in the separate attachment. 
> 
> I know that bigger properties sell for more, but I'm not sure how much it affects the price. Would you be able to help me to explore the data so that I can better understand what the data means; what it looks like. I also would like to better understand how the house prices are related to the square feet of the properties, in a general sense. Ultimately, I would like to use this data to help me make better decisions. For example, a client came to me trying to sell their 1500 square foot house for $300,000, which I think is a low price. Can this data help me to convince my client that the house should be sold for more, so that I can get a bigger commission? I am also talking to another client who is considering buying this massive 3750 sqft house! This client wants to know if the house price listed, $825,000, is reasonable among houses that size; can the model help me decide if the property is a good value?

### Analysis Summary

I did some numerical and visual exploration to know how the data looks like and what does it mean in general sense. I found that the predictor (Sqft) has a minimum and maximum value of 850 and 3262 with the average value of 1876.56 (Figure 1 & Table 1). Similarly, response variable (Price) ranges from $307,500 to $840,000 with a mean value of $507502.78 (Figure 2 & Table 1). In addition, I can say that the square foot is positively correlated with the Price (Figure 3) i.e., for every single unit increase in the square foot, the average price would be approximately $179.14 higher (Table 3).

#### Figure 1: Box plot - Sqft

![Figure 1](https://user-images.githubusercontent.com/37155988/93033716-723b9c00-f605-11ea-881f-1ebbd70b51a5.png)

#### Figure 2: Box plot - Price

![Figure 2](https://user-images.githubusercontent.com/37155988/93033718-723b9c00-f605-11ea-9319-31e5f0e177c1.png)

#### Figure 3: Scatter plot - Price vs Sqft

![Figure 3](https://user-images.githubusercontent.com/37155988/93033719-72d43280-f605-11ea-9710-d570953de2ab.png)

#### Table 1: Descriptive Statistics - Price, Sqft

![Table 1](https://user-images.githubusercontent.com/37155988/93033720-72d43280-f605-11ea-9bd8-e76dac6d4e5a.png)

#### Table 3: Coefficients

![Table 3](https://user-images.githubusercontent.com/37155988/93033722-72d43280-f605-11ea-842a-3e5c40322630.png)

Yes, this data can be used as an evidence to persuade your client that the estimated price of $300,000 is less for a house of 1500 square foot (Table 4). Although the possible individual prediction estimates would range roughly between $259,563.88 and $620,527.28 (which includes your client’s estimates), the average estimate range is roughly between $404,926.84 and $475,164.32 (which is more than your client’s estimate). This means that on average houses of 1500 square foot area are sold in the range of $404,926.84 and $475,164.32. Hence, your client should consider re-evaluating his/her judgement.

Unfortunately, the model is restricted to make predication for houses of area that ranges from 850 to 3262. The house in question with the area of 3750 square foot is larger than houses in the provided data. Conceptually, there could be other factors involved in predicting house prices of this big area such as house layout, useable space and potential future. For instance, the buyer of a large house may want to check the layout so that he/she doesn’t need to spend more on renovating the place which can be a really huge amount. In contrast, buyer of a small house may not need to worry as any modification won’t be that expensive given the house area. This might alternate the linear correlation that I see in the data currently. Thus, the model may mislead your second client.

### Appendix

#### 1) Statistical analysis:

I visualized the predictor and response in individual box plots to get the five-number summary (Minimum, First quartile, Median, Third quartile, Maximum). I discovered that the five number summaries of Price and Square foot are (307500, 394250, 502500, 585625, 840000) and (850, 1419, 1739.5, 2306.25, 3262), respectively. As the variables are linearly correlated (Figure 3), I defined the linear relationship between the two as the following:

     Y = β0 + β1X

where Y is the price in USD and X is the house area in square foot. β0 and β1 are the intercept and slope of the predictor, respectively.

Upon fitting the model, I got the estimated co-efficient β0 and β1 as 171331.47 and 179.14, respectively (Table 3). From table 2, I can note that the R square for this model came out to be .604 which means that 60.4% of the variability in this response is explained by this model. Although it is not ideal, I can still use the model to make the predictions. Similarly, the standard error of the estimate is 87111.55 which is not great either but still allowable relative to the mean of the house price.  

I then did hypothesize testing for both the intercept and slope at 5% significance levels (Table 3). For β0, the null and alternative hypothesis were as follows: H0: β0 = 0; HA: β0 ≠ 0. Since the P-value (0.001) is less than 0.05 at 5% significance level, I reject the null hypothesis i.e., β0 is statistically significant and cannot be equated to zero. For β1, the null and alternative hypothesis were as follows: H0: β1 = 0; HA: β1 ≠ 0. Since the P-value for β1 (0.000) is less than 0.05 at 5% significance level, I reject the null hypothesis i.e., β1 is statistically significant and there is some correlation between Square foot and Price.

It is important to note that this model is only limited to predictor values ranging from 850 to 3262 i.e., making predictions for anything less than or greater than that would be an attempt of extrapolation. Furthermore, only 60.4% of the variability in the model is explained by this model i.e., I may need to add more features to the analysis. Some of the additional variables to consider could be: 1) Distance from frequently visited places such as Supermarket, Hospital and Airport, 2) Age of the property and 3) Current state of local real estate market. 


