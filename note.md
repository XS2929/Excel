# Part One, histogram

Excel 2016 steps:
1. data paste into a sheet. 
2. find min, max, count.
3. get bin size and values according to the result in last step. 
4. from data Analysis tool choose **[Histogram]**.
5. set input data, bin data, output cell. Check label if needed. Check chart output Confirm graph generation. 
6. in the generated graph, adjust the gap between each bin to 0. 
7. analysis. Is it normal, left skewed or right skewed. Normal find mean and standard deviation. Skewed find median and IQR. 


# Part Two, one sample t test

Excel 2016 steps:
1. data paste into a sheet.
2. get count as sample size, count - 1 as degrees of freedom, standard deviation, standard error = standard deviation/sqrt(sample size).
3. calculate t statistic value, 

To find the p-value for a right-sided or greater than alternative hypothesis test:
	p-value: =T.DIST.RT([t stat],[DF])
	t-critical: =T.INV(0.95, [DF])
To find the p-value and t-critical for a left-sided or less than alternative hypothesis test:
	p-value: =T.DIST([t stat],[DF],TRUE)
	t-critical: =T.INV(0.05, [DF])
To find the p-value for a two-sided alternative hypothesis test:
	p-value: = T.DIST.2T([t stat],[DF])
	t-critical: =T.INV.2T(0.05, [DF])

For a 95% confidence interval, calculate t_star (t-critical). =T.INV.2T(0.05,[DF])
The 95 % confidence interval is found by using the equations =[mean] + (t_star × SE) for the
upper bound, and =[mean] - (t_star × SE) for the lower bound


# Part Three, Paired(Dependent) t-test

Excel 2016 steps:
1. copy paste the two columns to be analyzed
2. in the data Analysis tool, choose 't-test: Paired Two Sample for Means'. 
3. set range one as column one, range two as column two and check label if needed. 



# Part Four, Independent t-test

Excel 2016 steps:
1. copy paste the two columns to be analyzed
2. in the data Analysis tool, choose 't-test: Two-Sample Assuming Unequal Variances'. 
3. set range one as column one, range two as column two and check label if needed.


# Part Five, ANOVA

Excel 2016 steps:
1. copy paste the all columns to be analyzed
2. in the data Analysis tool, choose 'ANOVA: Single Factor'. 
3. set ranges and output.
4. if p value is less than alpha value, reject null.
 
if reject null, Post Hoc test is needed.
Do independent t test between groups, total of n(n-1)/2 comparisons needed. 
New alpha value = old alpha value / number of comparisons. 

If any independent t test has a p value less than new alpha value, those 2 groups are significant different. 


# Part Six, Chi-square test

Excel 2016 steps:
1. use insert --> pivot table to generate the Contingency Table, uncheck null 
2. insert pie chart for each category
3. calculate the expected value table and the difference table
4. calculate chi-square statistic value X = sum of (expected value - observed value)^2 / expected value
5. calculate degree of freedom: (number of row - 1)(number of column - 1)
6. get the chi square critical value, Excel build in function: =CHISQ.INV.RT(0.05,degree of freedom)
7. reject null if statistic value > critical value, that means the two categorical variables are not independent

# Part Seven, Scatterplot, Correlation 
Excel 2016 steps:

1. copy the x and y values into a new sheet
2. remove the records with missing values
3. use insert --> scatter to generate the scatter plot
4. to check whether the data is decently usable, use Excel built-in function correl(columnA, columnB) to check the correlation value
5. the R square is the square of the correlation value, which is used to interpret a model, "The model explain R_square*100 percent of the variation of y variable"
6. to check which kind of model is better, see next part


# Part Eight, Model Fitting 
1. right click the points on scatter plot and click data trend to get models like linear and exponential 
2. after show the R square and regression function from last step, choose text option to show 4 decimal values in model
3. if choose to generate an exponential model, the default format in Excel is y = a * e^(kx)
4. use built in function =exp(k) to cast the model with another non-e constant increase factor: y = a * b^(x)
5. use the R square value of different models to compare which model might be better

