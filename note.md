#Part One, histogram

Excel 2016 steps:
1. data paste into a sheet. 
2. find min, max, count.
3. get bin size and values according to the result in last step. 
4. from data Analysis tool choose **[Histogram]**.
5. set input data, bin data, output cell. Check label if needed. Check chart output Confirm graph generation. 
6. in the generated graph, adjust the gap between each bin to 0. 
7. analysis. Is it normal, left skewed or right skewed. Normal find mean and standard deviation. Skewed find median and IQR. 


#Part Two, one sample t test*

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


#Part Three, Paired(Dependent) t-test*

Excel 2016 steps:
1. copy paste the two columns to be analyzed
2. in the data Analysis tool, choose 't-test: Paired Two Sample for Means'. 
3. set range one as column one, range two as column two and check label if needed. 



#Part Four, Independent t-test*

Excel 2016 steps:
1. copy paste the two columns to be analyzed
2. in the data Analysis tool, choose 't-test: Two-Sample Assuming Unequal Variances'. 
3. set range one as column one, range two as column two and check label if needed.


#Part Five, ANOVA*

Excel 2016 steps:
1. copy paste the all columns to be analyzed
2. in the data Analysis tool, choose 'ANOVA: Single Factor'. 
3. set ranges and output.
4. if p value is less than alpha value, reject null.
 
if reject null, Post Hoc test is needed.
Do independent t test between groups, total of n(n-1)/2 comparisons needed. 
New alpha value = old alpha value / number of comparisons. 

If any independent t test has a p value less than new alpha value, those 2 groups are significant different. 






