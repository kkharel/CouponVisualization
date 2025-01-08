# Will the Customer Accept the Coupon?


Note: Since the github does not display plotly graphs, I used NBViewer to render the charts and graphs. Here is the link to the notebook:

[https://nbviewer.org/github/kkharel/CouponVisualization/blob/main/.ipynb_checkpoints/Coupon%20Analysis-checkpoint.ipynb]

Notebook file contains the detailed analysis and I will be highlighting only some of the findings here. 

Univariate analysis looks at the individual features and calculates the acceptance, rejection and relative rate without taking into account other features in the dataset. Along with univariate analysis, we further segment the analysis by coupon type. Then, we look at top 10% of customers by number of coupons sent and their contextual and user attributes. Next, we dive deeper into coffee house coupons to find patterns and the characteristics of customers who accepts and rejects the coupon. 

## Summary

### Overall
Customers accepted 56.8%of coupons and rejected 43.2% of coupons that were sent to them. The net success rate of coupons is 13.68%.

The net success rate (also known as relative rate) is calcuated as,

(accepted_count - rejected_count) / total_count

Net Difference (accepted_count - rejected_count) measures the net difference between the number of accepted coupons and rejected coupons by users. If the result is positive, it means there are more accepted coupons than rejected coupons. If it's negative then there are more rejected coupons than accepted coupons.

By dividing the net difference by total_count or total number of coupons, we are normalizing the value which makes it a proportion rather than an absolute value. This will help us compare the results across different groups where the total count may vary.

If the relative rate is close to 1, it tells us that almost all coupons were accepted. If the relative rate is close to -1, it tells us almost all coupons were rejected. If the value is around 0 then the number of accepted coupons and rejected coupons are roughly equal.

The formula mentioned above provides insight into the balance between acceptance and rejection rates in relation to total count, giving a normalized measure of preference or net success rate for coupons.

### Context Attributes

By analysis context features, we found the following insigts:

The top 10% of customers contributed 38.94 percent of total coupons

The top 10% of customers who rejected more coupons than accepted contributed 12.62 percent of total coupons

The top 10% of customers who accepted more coupons than rejected contributed 26.32 percent of total coupons

The context of top 10% of customers who accepted more coupons than rejected are...

| Index | Coupon              | Destination       | Weather | Temperature | Time | Passenger   | Direction Same |
|-------|---------------------|-------------------|---------|-------------|------|-------------|----------------|
| 1     | Coffee House        | No Urgent Place   | Sunny   | 80          | 2PM  | Friend(s)   | 0              |
| 3     | Restaurant(<20)     | No Urgent Place   | Sunny   | 80          | 6PM  | Friend(s)   | 0              |
| 4     | Coffee House        | Work              | Sunny   | 80          | 7AM  | Alone       | 1              |
| 5     | Carry out & Take away | Work            | Sunny   | 80          | 7AM  | Alone       | 1              |
| 6     | Coffee House        | No Urgent Place   | Sunny   | 80          | 10AM | Friend(s)   | 0              |
| 9     | Restaurant(<20)     | Home              | Sunny   | 80          | 6PM  | Alone       | 1              |
| 10    | Coffee House        | No Urgent Place   | Sunny   | 80          | 10AM | Alone       | 0              |
| 11    | Coffee House        | No Urgent Place   | Sunny   | 55          | 2PM  | Friend(s)   | 0              |
| 12    | Restaurant(<20)     | No Urgent Place   | Sunny   | 80          | 2PM  | Friend(s)   | 0              |
| 14    | Bar                 | Home              | Sunny   | 55          | 6PM  | Alone       | 1              |
| 15    | Restaurant(<20)     | No Urgent Place   | Sunny   | 55          | 2PM  | Alone       | 0              |
| 16    | Carry out & Take away | No Urgent Place | Sunny   | 80          | 10AM | Friend(s)   | 0              |
| 17    | Carry out & Take away | No Urgent Place | Sunny   | 55          | 2PM  | Friend(s)   | 0              |


The context of top 10% of customers who rejected more coupons than accepted are...

| Index | Coupon              | Destination | Weather | Temperature | Time | Passenger | Direction Same |
|-------|---------------------|-------------|---------|-------------|------|-----------|----------------|
| 0     | Coffee House        | Work        | Sunny   | 55          | 7AM  | Alone     | 0              |
| 2     | Coffee House        | Home        | Sunny   | 80          | 6PM  | Alone     | 0              |
| 7     | Restaurant(20-50)   | Work        | Sunny   | 80          | 7AM  | Alone     | 0              |
| 8     | Restaurant(20-50)   | Home        | Sunny   | 55          | 6PM  | Alone     | 0              |
| 13    | Bar                 | Work        | Sunny   | 55          | 7AM  | Alone     | 0              |


We divided user attributed in two parts and analyzed them separately.

### User Attributes 1

By analyzing the first User Attributes (Education, Occupation Group, Income Group, Coupon). The following insights were extracted for top 10% of users who received the coupon.

The top 10% of customers contributed 40.38 percent of total coupons

The top 10% of customers who rejected more coupons than accepted contributed 15.14 percent of total coupons

The top 10% of customers who accepted more coupons than rejected contributed 25.24 percent of total coupons

The customer attributes of top 10% of customers who accepted more coupons than rejected are...

| Index | Education                          | Occupation Group | Income Group       | Coupon                  |
|-------|------------------------------------|------------------|--------------------|-------------------------|
| 2     | Some college - no degree          | other            | low income         | Coffee House            |
| 3     | Bachelors degree                  | white collar     | low income         | Coffee House            |
| 4     | Some college - no degree          | white collar     | middle income      | Coffee House            |
| 5     | Bachelors degree                  | white collar     | middle income      | Restaurant(<20)         |
| 7     | Bachelors degree                  | white collar     | middle income      | Carry out & Take away   |
| 8     | Some college - no degree          | other            | low income         | Restaurant(<20)         |
| 10    | Some college - no degree          | white collar     | low income         | Restaurant(<20)         |
| 11    | Some college - no degree          | white collar     | middle income      | Restaurant(<20)         |
| 15    | Bachelors degree                  | white collar     | low income         | Restaurant(<20)         |
| 16    | Some college - no degree          | other            | low income         | Carry out & Take away   |
| 18    | Some college - no degree          | white collar     | middle income      | Carry out & Take away   |
| 19    | Some college - no degree          | white collar     | low income         | Carry out & Take away   |
| 20    | Bachelors degree                  | white collar     | upper middle income| Restaurant(<20)         |
| 21    | Bachelors degree                  | white collar     | low income         | Carry out & Take away   |
| 23    | Some college - no degree          | other            | middle income      | Coffee House            |
| 24    | Graduate degree (Masters or Doctorate) | white collar | middle income      | Restaurant(<20)         |
| 25    | Some college - no degree          | blue collar      | low income         | Restaurant(<20)         |
| 26    | Bachelors degree                  | other            | middle income      | Coffee House            |


The customer attributes of top 10% of customers who rejected more coupons than accepted are...

| Index | Education                          | Occupation Group | Income Group       | Coupon             |
|-------|------------------------------------|------------------|--------------------|--------------------|
| 0     | Bachelors degree                  | white collar     | middle income      | Coffee House       |
| 1     | Some college - no degree          | white collar     | low income         | Coffee House       |
| 6     | Graduate degree (Masters or Doctorate) | white collar | middle income      | Coffee House       |
| 9     | Bachelors degree                  | white collar     | upper middle income| Coffee House       |
| 12    | Bachelors degree                  | white collar     | middle income      | Bar                |
| 13    | Some college - no degree          | blue collar      | low income         | Coffee House       |
| 14    | Bachelors degree                  | white collar     | high income        | Coffee House       |
| 17    | Some college - no degree          | other            | low income         | Bar                |
| 22    | Bachelors degree                  | white collar     | middle income      | Restaurant(20-50)  |
| 28    | Bachelors degree                  | white collar     | low income         | Bar                |


### User Attributes 2

We further looked into second user attributes (Gender, Age Group, Marital Status) and found the following for top 10% of users.

The top 10% of customers contributed 41.50 percent of total coupons

The top 10% of customers who rejected more coupons than accepted contributed 9.42 percent of total coupons

The top 10% of customers who accepted more coupons than rejected contributed 32.08 percent of total coupons

The customer attributes of top 10% of customers who accepted more coupons than rejected are...

| Index | Gender | Age Group  | Marital Status       | Has Children | Coupon                 |
|-------|--------|------------|----------------------|--------------|------------------------|
| 0     | Male   | 21 to 30   | Single               | 0            | Coffee House           |
| 1     | Male   | 21 to 30   | Single               | 0            | Restaurant(<20)        |
| 2     | Female | 21 to 30   | Single               | 0            | Coffee House           |
| 3     | Male   | 21 to 30   | Single               | 0            | Carry out & Take away  |
| 4     | Male   | 21 to 30   | Single               | 0            | Bar                    |
| 5     | Female | 21 to 30   | Unmarried partner    | 0            | Coffee House           |
| 6     | Male   | 21 to 30   | Single               | 0            | Restaurant(20-50)      |
| 7     | Female | 31 to 40   | Married partner      | 1            | Coffee House           |
| 8     | Female | 21 to 30   | Single               | 0            | Restaurant(<20)        |
| 11    | Female | 21 to 30   | Single               | 0            | Carry out & Take away  |
| 13    | Female | 21 to 30   | Unmarried partner    | 0            | Restaurant(<20)        |
| 15    | Female | 31 to 40   | Married partner      | 1            | Restaurant(<20)        |
| 16    | Female | 21 to 30   | Married partner      | 1            | Coffee House           |
| 17    | Male   | 31 to 40   | Married partner      | 1            | Restaurant(<20)        |
| 18    | Female | 41 to 50   | Married partner      | 1            | Restaurant(<20)        |
| 19    | Male   | 31 to 40   | Married partner      | 1            | Carry out & Take away  |
| 21    | Female | 21 to 30   | Single               | 0            | Bar                    |
| 22    | Female | 31 to 40   | Married partner      | 1            | Carry out & Take away  |
| 24    | Female | 21 to 30   | Unmarried partner    | 0            | Carry out & Take away  |
| 27    | Male   | 31 to 40   | Married partner      | 0            | Coffee House           |
| 29    | Female | 41 to 50   | Married partner      | 1            | Carry out & Take away  |

The customer attributes of top 10% of customers who rejected more coupons than accepted are...

| Index | Gender | Age Group  | Marital Status       | Has Children | Coupon        |
|-------|--------|------------|----------------------|--------------|---------------|
| 9     | Male   | 31 to 40   | Married partner      | 1            | Coffee House  |
| 10    | Male   | 21 to 30   | Unmarried partner    | 0            | Coffee House  |
| 12    | Female | 41 to 50   | Married partner      | 1            | Coffee House  |
| 14    | Male   | 31 to 40   | Single               | 0            | Coffee House  |
| 20    | Female | 21 to 30   | Unmarried partner    | 0            | Bar           |
| 23    | Female | Above 50   | Married partner      | 1            | Coffee House  |
| 25    | Male   | 31 to 40   | Married partner      | 1            | Bar           |
| 26    | Female | 21 to 30   | Married partner      | 0            | Coffee House  |
| 28    | Male   | 41 to 50   | Married partner      | 1            | Coffee House  |


### Coffee House Coupons Summary

Then, we decided to drill down into coffee house coupon and look at various combination and permutation of feature and its values and derived the following insights.

We have compared only few of the features with each other for coffee house coupons. There can be many permutations and combinations of feaures and its values and it is not optimal for us to evaluate all of these. I only looked at few of the features to hypothesize about the customers who were sent the coffee house coupons. I evaluated these customers based on nunmber of visits and grouped them based on whether they rejected more coupons than accepted or accepted more coupons than rejected and again compared them along with other features. Below are the insights that were drawn from the above analysis.

The overall acceptance and rejection rate is roughly equal for coffee house coupon hence we are looking deeper to find patterns ad characterics of customers.

When we segment the coffee house coupons by number of times customer visits the coffee house in a month, we can see that the customers that visits the coffee house one to three times, four to eight times and greater than eight times accepts more coupons than they reject. Customers who rejects the most coupons than accepted are the ones who never visits the coffee shop or visits coffee shop less than once a month. The overall acceptance rate of customers who accepts more coupons than rejected is ≈66% and their rejection rate is only ≈34%. The overall acceptance rate of customers who rejects more coupons than accepted is only ≈34% and their rejection rate is only ≈66%.

Based on the univariate analysis, we saw that the age group that is below 21 accepted more coffee house coupons than other age groups. So, we further looked into this age group within the coffee house visit group of accepted more than rejected and rejected more than accepted. The acceptance rate for accepted more than rejected group who are below age 21 is ≈75% and their rejection rate is only ≈25%. Note that there are few numbers of customers that falls into this group. On the other hand, the acceptance rate for accepted more than rejected group who are not below age 21 is ≈65%and their rejection rate is only ≈35%.

We also see that the age group 21 to 30 are sent the highest number of coffee house coupons and are also the ones with highest acceptance rate. But the age group above 50 has the highest net success rate than other age groups excluding below 21. The number of customers who are below the age of 21 that falls under rejected more than accepted group is relatively very small. The customers who are not below the age of 21 that falls under rejected more than accepted group had the acceptance rate of ≈34%.

For the income analysis, we looked at customers that accepted more than rejected and rejected more than accepted group along with customer income group specially low income group. The choice of low income group comes from univariate analysis results. We found that the acceptance rate of customers who accepts more coupons than rejected and are in low income group is ≈69% and the rejection rate is ≈31% overall. We also found that acceptance rate of customers who accepts more coupons than they reject and are not in low income group is ≈64% and the rejection rate is ≈36%. The difference in acceptance rate between these two groups is ≈5%. The difference in acceptance rate for customers who rejected more coupons than accepted and are in low income group and also who are not in low income group are roughly equal suggesting that there is no difference between these two groups.

We further drilled down on income analysis along with the customer destination to answer the question around customer income and their destination. Now, we added one more variable for analysis that is destination. We find that customers who are in accepted more than rejected group , not from low income group and are going to work had acceptance rate of ≈57% and rejection rate of ≈43%. We also looked at customers who are in accepted more than rejected group, from low income group and are going to work. Their acceptance rate is ≈71%. We can conclude that customers from low income group who are going to work seems to accept more coffee house coupons than other groups.

From univariate analysis, we also found that customer that are in accepted more than rejected group for coffee house visits also accepted more coupons than rejected for expensive restaurants. For this analysis, we did not include all the visits that results in more accpeted coupons than rejected for expensive restaurants. We only looked at customers who visited expensive restaurant more than eight times a month and white collar occupation against all others. We found that the acceptance rate of customers who accepted more coupon than rejected, visits expensive restaurant more than 8 times a month and does white collar job is ≈74% but the number of coupons sent to these customers are low compared to other groups. When the customer does not visit expensive restaurant more than 8 times a month and does white collar job for accepted more than rejected group, we found their acceptance rate of coupon to be ≈62%. Customers who accepted more coupon than rejected, visits expensive restaurant more than 8 times a month and is not from white collar job has the acceptance rate of ≈39% . The acceptance rate of Customers who accepted more coupon than rejected, does not visit expensive restaurant more than 8 times a month and is not from white collar job is ≈72%. We also found that we do not have customers who rejected more coupons than accepted, visit expensive restaurant more than 8 times a month and is from white collar job group.

### Next Steps
Since there are many combinations and permutations of unique values of features, we cannot possibly visualize everything to derive insights into customer characteristics. The visualization can provide a guide towards more mathematical approach of machine learning. For next steps, we can build the classification model for this given problem to predict whether the customer accepts the coupon or not? However, machine learning model needs massive amount of data to make correct prediction, this alone might not be a good solution. We can explore some sampling techniques or create more synthetic dataset to train the machine learning model and compare the results between various models and pick the one that best predicts the behavior of the customer.
