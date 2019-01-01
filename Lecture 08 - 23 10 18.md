# Lecture 8 - 23/10/18

## Intro

- Ideas from market economics give us new tools and methods for computer science, especially those to do with managing scarce resource in fast-changing environments
	- This is called Market-Based Control (MBC)/M-B Resource Allocation (MBRA)
	- It gives fast, robust distributed control for problemsn that can dynamically vary over time

<br> 

- To implement these, we'll need two things
	- Software traders - to quote prices and haggle
	- Marketplaces - where buyers and sellers can meet and trade
- Designing these is hard, but the design process can be partially automated
- Automated traders developed for MBC can be used in real-world financial markets

## Economics

- Macroeconomics
	- High-level things
	- e.g. relationship between a nation's inflation rate and unemployment levels etc.
	- We won't cover it in this course
- Microeconomics
	- Basically maths
	- Theories to understand how scarce resources are allocated and prices/markets in this process

## Relevance to CS

- There are many systems that deal with allocation of scarce resources
- For example
	- Telecoms network - bandwidth is limited by the capacity of the system
	- Operating system - multiple processes competing for CPU, RAM, memory space etc.
	- Logistical systems - e.g. staffing/timetabling - all constrained by number of people, time slots etc.

MBC is not a new idea - it has been explored by other computer scientists

## Supply and Demand

- We're used to the idea of a supply shortage and the price going up - this is colloquially known as a seller's market
- If there is a supply excess then the price will fall - known as a buyer's market

These illustrate that the price of an item can be thought of as a function of the quantity demand and supplied

Some key terms

- Demand - the price buyers are prepapred to pay at each possible quantity
	- This is plotted on the graph of price vs quantity as a demand curve
	- This usually slopes downwards - as price increases the quantity demanded decreases
- Supply - the price sellers are prepared to sell for at each possible quantity
	- This is plotted on the graph of price vs quantity as a supply curve
	- This usually slopes upwards - as price increases the quantity supplied increases

![high_price](https://lh3.googleusercontent.com/r3ZS5rwrjacP-T29dkhqdTuqBgIi-pNZVsYEHpKH99jOY5sqpJsK0nKJa216gmGmkUAPAGX2Obmy)
- If we look at a high price $P_{Hi}$ it intersects at two points
	- On the demand curve we get $Q_{Dem}$ 
	- On the supply curve we get $Q_{Sup}$
- $Q_{Sup} > Q_{Dem}$ - there is a quantity surplus
- We know that in this situation, competition among sellers will drive price down

![low_price](https://lh3.googleusercontent.com/2dmu7z0BhJ5x9XeybaAIWFHe9LKaFkehUDl5Jes_IgMBXmOY61Cz2ouSv-58h_FjTTgxPMjvgKcB)
- If we look at a low price $P_{Lo}$ it intersects at two points
	- On the demand curve we get $Q_{Dem}$ 
	- On the supply curve we get $Q_{Sup}$
- $Q_{Dem} > Q_{Sup}$ - there is a quantity shortage
- We know that in this situation, competition among buyers will push the price up

![equilibrium](https://lh3.googleusercontent.com/BAFKvGIaGRzlP7MAoR9jZ0VD2gD4ZNLR0hVukYYrfA2jd1dRohzN1TR6LBCFBTDc2aID_39xPVeo)
- The two opposing pressures on the price balance out at an equilibirium point
- This is the price where $Q_{Sup} = Q_{Dem}$
- From this we get a price $P_0$ and quantity $Q_0$

This self-correcting nature of markets can result in efficient allocation of resources in an efficient decentralised manner

What does efficiency mean? One definition is Pareto Efficiency -

- No-one can be made better off without someone being worse-off - i.e. not one of the following two scenarios
	- Transaction prices being consistently above the equilibrium price would mean the buyers are being ripped off
	- Transaction prices being consistently below the equilibirium price would mean the sellers are being ripped off

In free markets each trader acts in their individual interest, and this can give rise to Pareto efficient allocations - but not always! (e.g. if a single seller has a monopoly)

Note that Pareto efficient allocations aren't always morally fair

## Auctions and Traders

- An auction is a mechanism where buyers and sellers come together to agree a price for a trade
- There are many types of auctions
	- English (ascending bid)
	- Dutch (descending bid)
	- Retail (posted offer) - even though we usually wouldn't think of shops as an auction!

## CDA

The continuous double auction (CDA) is very interesting example

- Any buyer can announce a bid price at any time
	- This is expected to increase over time
- Any seller can announce an offer price at any time 
	-  This is expected to decrease over time
- Any buyer and seller is free to accept a bid/offer at any time
- There may be a fixed end to the market closing

The CDA is interesting for two reasons

- Traders in a CDA rapidly and robustly converge on the market's theoretical equilibrium price
	- Despite the fact that none of them know that price and they're all acting selfishly
- The CDA is the mechanism that most of the world's major markets use

The CDA has transformed over time - from rooms of people, to telephone calls, to computer bids, to software traders

### The Reality of Economics

![simplification](https://lh3.googleusercontent.com/TqzPaN8k_q7OmIGni0fR72jn84OnEEkzF0jv7rQG_yqGdHhZSQwUObeQNR2whjBqQnpQNj3uG2N7)
This is a simplification that is useful for teaching purposes, but not true to life in CDA markets

![stepped_curve](https://lh3.googleusercontent.com/lNQwubiOYSOU3CZglLK7WECsopNnucZEhxKi3VcbP93wRajLCRkQ1ruVk33GpW63lkpvzc_a3JIN)
A typical CDA curve

- The supply and demand curves are stepped
	- We have a relatively small number of units in the market
	- Each step represents an additional unit available for sale
	- Each step in the demand curve indicated an additional units desired
- Our simplification above is like a zoomed out version of this
- But this is still a simplification!
- In reality
	- People bid below their price they're willing to pay
	- People offer above their price they're willing to sell at
- The difference is the utility for the trader - often said in terms of "bought at $X\%$ margin

![triangle_curve](https://lh3.googleusercontent.com/_M4HRhULImccN3BMVpet_4srTi8E_BgdPJdueLsBVz8lHWlzLgyqFEj0JQhxDwmbT4AmY67kcwIr)
- We need to account for the fact that *everyone is lying*
- Shaded triangles represent the utility margins that the traders are trying to trade at
	- The horizontal edge of the triangle rest on the limit of that part of the curve
	- The apex of the triangle points to the $\text{price} + \text{margin}$ that the trader will quote in the market at any time
- Remember that traders in the auction can only see the quoted prices, not the hard limits - these are secret
- So the curves you can stitch together using the prices in the market, may significantly differ from the true underlying curves given by those hard limit prices
	- So the intersection may actually be a different price

![triangle_curve_2](https://lh3.googleusercontent.com/z1GkuyavexB9J1B9W3wDzeSq-No7BplxxAOYKoGOmxLHunILBV-0s7aDXgBTKaCEj0LhqWu6BoC9)
- That kind of curve also doesn't hold for very long - the traders neares the equilibirium price will trade and leave
- So we can redraw the curve taking this into account
- This will happen after every transaction, and new buyers and sellers can appear at any time

![comparing_curves](https://lh3.googleusercontent.com/5wxH9ENP8_k6cO-hXtT-21kiVyMaLspKdBfA7YP1l7ZTlQ90R-XQLvZS8yCNydKqBwjx9HYWvO7L)
- We want to compare the changes and see which things we have to consider
- The vertical extend of each triangle represents the margin that each trader is trying to get - the utility they're trying to gain
	- Smart traders will adapt their margin depending on the market

![changing_curves](https://lh3.googleusercontent.com/MCCLianOQbaQ6JWkY_6FnlALwINxIiL7qKZutZ-Cjdi-L8KvfAB6mzU-pCDRR_S7qbCu9ZEnAj-c)
- Here traders have changed their margins over time
- Traders whose limit prices are favourable in comparable to the equilibrium price have capitalised on it and increase their margins
- Traders whose limit price is on the wrong side of the equilibrium price have had to reduce their margins to try and secure a trade
- This model is still not completely true to life but is very useful in theoretical research

## Experimental Economics

- Vernon Smith pioneered (and won a Nobel Prize) for the labratory-style studies of human market-trading behaviours
- A number of human subjects are either 'buyers' or 'sellers'
- Each trader is given a private instruction - their limit price
	- By giving different limits, different types of supply and demand curve could be introduced into the market
- Traders then interact in a market mechanism - any buyer/seller prices that cross each other's threshold will trade
- In CDA this demonstrates rapid equilibriation
- The end time marks the end of the trading period, and another trading period can commence
- Traditionally an experiment will consist of 5/6 10-minute trading periods
- Note that professional traders tend to do slightly better in these experimence than naïve subjects

### Smith's Results

![smith_results_1](https://lh3.googleusercontent.com/4cc1NZUmSqksM-I0oEVXhyZJlBle7ii-nHhbKtwVcjCJvq3aZ8k-2e9GePkD2wM5SjSelTX_4YBX)
- The supply curve is seen in red, demand curve in blue
- The right-hand side shows a time series of transaction prices
	- The numbers on the bottom show the number of transactions in the day
- The shaded grey bit shows the amount of utility that would be extractable from the market under idea conditions - Smith called it the 'surplus in the market'
- We can see that price converges towards the equilibrium over the course of a few 'days' and then stays there

![smith_results_2](https://lh3.googleusercontent.com/xNQC_wtNflOOZf0bFpvo_IsMwG1ND8dlflYCXd5W-4vwZjXAi1zPwmNyU6JlT4rd-DEnKOEnNL6h)
- Here Smith experimented with flattening the supply curve
- The transcation price trajectory alters - they approach from above and remain above the equilibrium through the experiment

### Metric for Markets

- Smith's $\alpha$ - the root mean square deviation of transcation prices around the theoretical equilibrium price as a percentage (lower is better)

$$\alpha = \frac{100}{P_0}\sqrt{\sum_{t \in T} \frac{(P_1 - P_0)^2}{\lvert T \rvert}}$$

- Allocative Efficiency - total utility earned by all traders, divided by the theoretical maximum possible total utility as a percentage - determines how effective the market is at extracting 'gain through trade'
- Single Agent Efficiency - a profit earned by an agent, divided by its expected profit if ll trades take place at the equilibrium price - looks at performance of individual agents, including exploiting other agents

The allocative efficiency of a market can never be greater than $100\%$, but the single agent efficiency can be

### Studying How Intelligent Traders Need to be

- A very influential paper by Gode and Sunder looked at experimental studies they conducted to see how much of the allocative efficiency of a market is down to the traders and how much is due to the market mechanism
- They set up a sequence of experiments, first with humans and then the same experiments but with software - zero-intelligence (ZI) traders
	- ZI-U - 
		- Unconstrained
		- Quote any price at all, chosen randomly between 0 and a system-wide maximum price
		- They were completely useless
	- ZI-C
		- Constrained
		- Generate a random price but not one that would enter into a loss-making deal (i.e. between trader price and system max price)
		- They were surprisingly human-like
- The allocative efficiency of ZI-C markets was pretty much the same as that of human markets
- They drew the conclusion that maybe allocative efficiency wasn't a good measure of intelligence of traders in the market
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NjA3MDM0NzAsMTcxMzQ4Mzg5MywtMT
MyODM0NzIxMiw4Nzc4NjA3OCwtOTQ0MDcxMjgyLC0xNTIyOTMx
NzAyLDIwNjcyNTM3Myw5MjgwMTkzNjMsLTE5MDQ4NTIwMTksMT
I0NTEzMDAxMiwtMTE3ODIwNDAwMCwtMTQyNDcyMjI3NCw5NjM2
MjI1OTYsMTAwOTMzOTgwMiwxNDkzMTk5MjksLTE3ODEyMjg3Mj
YsMTcyMzU2ODEzNiwtMTY4NzE5ODQxMSw3MzA5OTgxMTZdfQ==

-->