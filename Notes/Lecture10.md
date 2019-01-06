# Lecture 10 - 30/10/18

## Intro

- When running experiments (such as on BSE) we start to treat the autonomous agents as objects of empirical study
- This approach uses analysis of empirical data, rather than derivation of formal proofs and this approach is common in advanced IT systems engineering
- Many modern technical and socio-technical systems are so complicated that it is often impracticle or impossible to produce a useful theoretical analysis of those systems
- But there is a genuine need for principled, quantitative characterisation or comparison of these systems
- The best path forward for this is to treat the system as if it is a natural-occurring phenomenon and then run experiments on it

> Book recommendation - Math on Trial - Schneps
> Book recommendation - The Art of Computer Systems Performance Analysis - Jain
> Book recommendation - Statistics in a Nutshell - Boslaugh
> Book recommendation - Design and Analysis of Experiments - Montgomery

## Basic Statistics

### Measures of Central Tendency

- Median
	- The 'midway' value
- Mode
	- The most likely value
- Mean
	- The average
- Sample Variance
	- Spread of data around the central tendency

We're taught the definitions, but not the limitations

![enter image description here](https://lh3.googleusercontent.com/WmrERTpa_x9Xk5dJHqK5o1lf3OJvh5I-RLL5O3jzMNPLdzTC2O0SuRrPB1zmkYlOKxjRjva0K0BF)
Not all distributions are nice though, for different distributions we'll need a different set of analytic tools

### Percentiles

- Percentile
	- $p$-percentile is the value below which $p$ percent of samples fall
- Quantile
	- Splits into 100 different divisions
	- All the others are just versions of this!
- Quartile
	- Splits into 4 divisions

### Non-Parametric Statistics

- Many statistical tests - 'parametric tests' - such as the t-test make underlying assumptions about the data
- Nonparametric techniques assume little or nothing about the udnerlying distributions - they need less testing/justification of assumptions

### Confidence Intervals

- Say we take a sample of $10$ sample values from some process with some variation in it
- We can calculate the mean of those samples and that sample mean can serve as an estimate of the population mean
- If we then take another $10$ samples and get a mean from that, it's likely to be different
- Repeating this will likely give different sample means every time
- This can go on forever!

Instead we can stop after a while and make a claim that the population mean lies within some range, and express how sure we are about that claim as a probability

This is a formalised as a *confidence interval*

- $[c_1, c_2]$ is the confidence interval
- $\alpha$ is the significance level
	- $0 < \alpha < 1$

The key thing to remember is that smaller $\alpha$ give larger values of the confident level

#### Computing Confidence Intervals

- One way to compute CIs is to take a lot of samples and compute the percentiles
	- So if we want a $90\%$ CI we get this from $c_1 = (\text{5-percentile})$ and $c_2 = (\text{95-percentile})$
- Another way it to use the central limit theorem
	- i.e. if we take enough sample means, the distribution of those means will converge towards a normal distribution, whose mean is the population mean

#### Using CI to compare two alternatives

When looking at two methods, calculating the CI on mean of samples from both can save a lot of time

![enter image description here](https://lh3.googleusercontent.com/VxhrKBvWDFsVCNY9eDbzpg0qR97nueZajcWfB0Ez7ck1U7q130RBLAmWNSUQRo4C9hOxU8d5Gtno)
If the confidence intervals don't overlap at all then it's evidence that one is better than the other

![](https://lh3.googleusercontent.com/tmbbevsY6GlkLd5wOP0Zdm8yHMshRO03_ZU6CQ3bxBnseyFGgip1guVoVQm-ik2a7m9Aw4X6KHim)
If the confidence intervals overlap and the mean of one is within the other, then we can say that at the stated confidence level, there's no statistical evidence of difference

![enter image description here](https://lh3.googleusercontent.com/2hAuXJTml5rLAlc-Kq_RsWG6pEjxL9Cpopt0bpW2v0dfaWguTZznLjpsLtQkUqGN1ak8HpnoC6Ie)
If the confidence intervals overlap but the means are outside the confidence intervals of the other, then another test is needed to establish stastical difference or sameness

### Wilcoxon-Mann-Whitney U Test

- Used for test $H_0$ that data in two samples come from the same population
- A non-parametric version of Student's t-test
- Uses medians instead of means - no assumption of normal distribution

Method -

- Combine $A$ and $B$ into one list but keep track of which list it came from
- Record number of datapoints in $A$ and $B$ as $n_1$ and $n_2$ (where $n_1$ is largest)
- Rank list from lowest to highest
	- Tied values are awards the average of the ranks
- Separate back into samples $A$ and $B$ and then sum rank values to get rank-sums $R_1$ and $R_2$
- If $H_0$ is true, you'd expect $R_1$ and $R_2$ to be roughly the same
	- This is formalised by computing $U_1$ and $U_2$
	- $U_1 = n_1 \cdot n_2 + ((n_1(n_1+1))/2)-R_1$
	- $U_2 = n_1 \cdot n_2 + ((n_2(n_2+1))/2)-R_2$
	- $U = \min(U_1, U_2)$
	- Compare $U$ to a critical value - if less than reject $H_0$

Not that you can't use this test to test multiple samples - it'll decrease the probability of your result being correct!

> Book recommendation - 100 Statistical Tests - Kanji
> Book recommendation - Data Analysis with Open Source Tools - Janert 
> Follow-on video - [Hans Rosling Ted Talk](https://www.ted.com/talks/hans_rosling_shows_the_best_stats_you_ve_ever_seen/up-next?language=en)
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzg2ODE0MDExLC0xOTMxNDc2NzQ0LDIxMj
Q2MTIzNTEsLTQwNzkyMjU1MiwxNjI0OTQ4MzE3LDE5NTU0MjUw
NDYsLTc0NjQwOTM5MywyNTM0OTA5MTUsLTIxMzA3MDA2NDAsMT
U2Nzc2ODM0NywxNjAxOTQ5OTQ1LC0xMjI5ODg1MjQyLDMwMTY5
ODMyMiw3MzA5OTgxMTZdfQ==
-->