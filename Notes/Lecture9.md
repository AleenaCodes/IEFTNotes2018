# Lecture 9 - 30/10/18

## Experimental Economics (cont.)

### Zero Intelligence

An argument for how ZI-C traders converge on equilibrium

![](https://lh3.googleusercontent.com/D3vQcS67t4wFlnXortDq4JnMWuf3_50lWKLx-vqn7sVi9czXjtKtUOeHcmGLkY6BNz7Loev6XtxM)
- ZI-C traders quote from the seller limit $S_{min}$ to the system max $P_{max}$

![enter image description here](https://lh3.googleusercontent.com/_-m4U7uZVTe0qDEcOkO36zzgdr_R1ic1ztyVGSWHTbdgGZSeZD7VvM1cfaGVBV-55FsM4QUUM1B6)
- So we can get a probability density for the offer prices

![](https://lh3.googleusercontent.com/v5R9rfcG8B7-8v0-eK5AyXYYSizrQ4evGt7hoUC-oxqR95qU5s3W9mM7FYeJQU2lV-xrY_8RYtvz)
- We can get the same probability density for the bid prices

<br>

- We can observe that a trade occurs in the ZI-C market only if the buyer's bid price is greater than a seller's most recently quoted offer, and vice versa
- This is known as 'crossing the spread'

![enter image description here](https://lh3.googleusercontent.com/Qr_nES45KyMgTXKAj1lLWnVnSlaQkVWwIYVyMqdww7_DkXsOqq7cQcYnh7Zn78qNBpzwjumHyw6e)
- The pdf for the transaction prices is given by the intersection of the bid pdf and the ask pdf
- In this example there is roughly symmetric supply and demand curves so the expected transaction price $E(p)$ is close to the equilibrium price

#### When ZI-C doesn't work

![enter image description here](https://lh3.googleusercontent.com/z21R9_ZRNO1l5Mm-CTMjhmjP_eMOdC-4no_plXbOF8KCU0SbeulR6n8MKkU3plBYL_ot_z27urNj)
- When the transaction price pdf is not symmetric about the equilibrium price, the $E(p)$ will different significantly from the equilibrium price $P_0$
- These are situations where ZI-C traders won't reach an equilibrium price - we need a better trader!

### ZIP Traders

- ZI-Plus (ZIP) traders
- Use the same price limits as ZI-C traders
- But use machine learning to adapt - try to increase profit margin

<br>

- Experiments run using the ZIP traders succeeded where ZI-C traders failed
- They resulted in more human-like market dynamics than ZI-C
- ZIP is now used as a benchmark against which more advanced strategies can be evaluated
- Further experiments in 2001 showed the ZIP traders could *beat humans*

#### Summary of the ZIP Algorithm

- For sellers there is a limit price $L$
- The price asked $P$ is $L$ plus some profit margin $M$
	- So $P=(1.0+M)L)$
- If your current proposed price is $P$ and either
	- Sellers are accepting bids below $P$
	- Sellers are making offers below $P$
- Then decrease $M$
- If traders are happing at prices above $P$, then increase $M$ (even if you currently have nothing to sell)
- The buyers do the inverse of this

#### Machine Learning in the Algorithm

- The amount by which $M$ is adjusted is determined by a learning rule - Widrow-Hoff with momentum
- The momentum factor dampens down responses to high-frequency changes in the target price

So ZIP is adaptive - it adjusts behaviour according to other traders' actions

### Kaplan's 'Lurking Sniper' Trader

- Kaplan's algorithm was entered into a competition for trading agents
- It sits in the background doing nothing until one of the following happens
	- A bid-offer spread drops to a sufficiently small value
	- The offer is less than the smallest transaction price in the previous period
	- There is not much time until the market closes
- If any of these conditions are fulfilled, the sniper jumps in and 'steals the deal' as long as it makes a profit greater than its minimum threshold

It won the competition, but is essentially parasitic - requires other types of traders in the market

### GD Traders

- Based on computing an estimate - a mapping for each possible price of a quote of a bid or offer, to what the probability is of a quote at that price being accepted by a counterparty
- This is called the belief function
- The belief function for history $H$ of $n$ recent trades is computed by

$$f(p) = \frac{able(p)+ole(p)}{able(p)+ole(p)+rbge(p)}$$

Where

- $able(p)$ is the number of accepted bids $\le p$ in $H$
- $ole(p)$ is the number of offers made $\le p$ in $H$
- $rbge(p)$ is the number of rejected bids $\ge p$ in $H$

Another paper was later published stating further improvements in GD traders

### Comparing Trading Algorithms

- Algorithms need to be compared against one another
- In the next lecture we'll explore empirical studies (simulation experiments) and analysing the results from these
- It can be usueful to look at markets homogeneously populated by specific trader algorithsm, but this is implausible in a real-life market

### Agent-vs-Agent Trading Contests

A paper in 2001 presented three types of tests

- Homogeneous population test
	- Every trader in the market is running one strategy
	- Provided baseline performance metrics for comparison
- One-in-many test
	- One different trader in an otherwise homogeneous population
	- Explores vulnerability of an algorithm to defection/invasion
	- Explores if other traders will defect, or will the population settle on a mix
- Balanced-group tests
	- Traders split evenly between two types
	- Each trader agent has a counterpart of the other type with identical limit prices
	- The paper argued this was the fairest way to test two algorithms against one another

From running these tests with the algorithms discussed above, the results show

- Kaplan is only good if there are a small number among a larger population
- ZI-C does poorly all the time
- MGD and ZIP seem to be roughly equal - which one wins depends on the circumstances

IBM ran experiments on 'replicator dynamics' where agents could switch strategies during the experiment, they found that a market that starts with a population of ZIP, GD and Kaplan traders in any ratio will eventually converge of a stable mix of either
	- 60% Kaplan, 40% ZIP
	- 30% Kaplan, 70% GD

IBM later published a paper showing that an algorith GDX (a modified GD algorithm) was the best-performing algorithm at the time

### AA Algorithm

- The Adaptive- Aggresive algorithm bears a resemblance to ZIP, and shares its used of the Widrow-Hoff learning algorithm
- Adapts its aggresive over time rather than profit margin
- How quickly it changes its margin in response to market conditions is described as its 'aggresiveness'
	- A more aggressive trader will change more quickly
- The paper showed that AA dominates ZIP and GDX, and also human traders

### ZIPOJA (Not reviewed)

- Vach's research in 2015 showed that AA did not always dominate as previously thought

## Bristol Stock Exchange

- Specifically developed for this unit, students can use the BSE to run experiments with traders
- It simulates a trading environment, with a Limit Order Book (LOB)

> Recommended book about automated trading - Why Arent' They Shouting by Kevin Rodgers
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk5NjM5OTYxMiw3OTkyMjMyNTMsMTQ4Mz
k1Nzk3NywtMTU0NzQ1MTY1MiwtNTM0Mzg2NTMzLC0xMTQ5MTgw
OTQxLC0xMDI2Mzg4NTg5LDMyNTM0MTIwMywxNjM0MzMwMTEsNT
gyNTQzMTM4LC05NzU1MDY2OTMsLTM3MTcwNTkzNiwxNTIxNTk1
NTkwLC01ODIwNDQ3MDksLTc3Mjc2NTc1MSwxMjI2Mzg5MTMwLD
czMDk5ODExNl19
-->