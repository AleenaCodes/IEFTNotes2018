# Lecture 14 - 13/11/18

## The Crowd Economy

- The "crowd economy" refers to economic and financial systems that use the crowd in some way
- Some examples crowd intelligence, mass collaboration, crowdfunding etc.

## Web 2.0

- Web 1.0 - 1990's
	- Main static sites
	- Most people were users rather than creators
- Web 2.0 - 2000's
	- User contribution/participation - YouTube, Wikipedia etc.
	- Dynamic programming languages - Python, Ruby, Perl
	- Social networks
	- Rich user experience, dynamic content, scalability
	- Facilitates easy collaboration as crowds

### Decentralising the web

![enter image description here](https://lh3.googleusercontent.com/bfdfHx6U2CdZNUqAlJQ8Tu1EAOuHy3EyjGixLt2skOoK_qsOKw61oM574PImXSkepSTawFeXV0Fj)
- Can think of the change from web 1.0 to web 2.0 as decentralisation
- The initial web was very centralised - people had their own servers (e.g. a company had one) and everyone would connect to this one server
- Over time moved to decentralisation, decentralised clusters of people interacting together
- Moving to distributed network where collaboration is possible
- People becoming collaborations *prosumers* - producing and consuming

Advantages -

- These distributed networks are also more resilient - any single node (e.g. a user/provider) can go down as the rest of the network will cope with it. This is in contrast to a centralised network which has a single point of failure
- It's easy to add a node to these networks e.g. a new Uber network can enter the network easily. In a centralised network there is a bottleneck for adding new nodes

## Prediction markets

- These are exchange-traded markets created for the purpose of trading the outcome of events
- They are a form of crowd intelligence
- "Crowdsourcing" prediction - way to try to get accurate predictions of an event ahead of time
- Used for elections etc.
- Can't ask something where you won't know the outcome at some point - has to be something with a fixed end date that can be verified in the real world
- Should be noted that prediction markets are very similar to betting markets - so much so that a betting licence is needed for it in some parts of the world

Process is as follows -

- Create some kind of fictional stock - each stock will be whether some event in the future is going to happen
- Allow people to trade units of that stock based on real-world event
- There are two mechanisms that can be used
	- Winner-take-all - paying if something happens
	- % payment - based on quantitative outcome e.g. a share of a vote
- Based on what people think will happen they may decided to buy or sell the unit
- The market is run like a CDA - participants state their buy/sell prices and trades take place when a crossing occurs
- The price of the unit can be thought of as the 'belief of the crowd'
	- A high price indicates that the crowd believes there's a high probability of that even happening

The belief is that because people are trading money their opinions will be less biased - considered more accurate than opinion polls

### IEM

- An example of a prediction market is the Iowa Electronic Market (IEM)
	- The only prediction market in the US that is allowed to use real money (some others use play money such as the Hollywood Stock Exchange) 
	- A non-profit market by the University of Iowa that is designed for resarch
	- Uses real money but has a hard limit - $500
	- Typically only several thousand users in each market

### How They Work

- Predict which of two candidates $A$ or $B$ will win an election
	- These things are mutually exclusive
- Create two futures contracts $C_A$ and $C_B$
	- Each share of $C_A$ will pay out $£1$ if $A$ wins and $£0$ otherwise
	- Each share of $C_B$ will pay out $£1$ if $B$ wins and $£0$ otherwise
- Contracts initially offered by allowing any trader to buy one share of each for $£1$
- Then allow users to trade shares, using a CDA mechanism
- A simple trading stategy - if your opinion is that candidate $A$ will win with probability $p$ (your expected value for $A$ winning is $p$)
	- Buy $C_A$ when the price $C_A < p$, buy $C_B$ when the price $C_B < 1-p$
	- Sell $C_A$ when the price $C_A > p$, sell $C_B$ when the price $C_B > 1-p$

There are some rules in the IEM -

- Can't "short-sell" - have to own the contract to sell it
- Can't "buy on the margin" - can only buy shares with money you already have

Prediction markets can work with more than 2 outcomes - just have contracts for each mutually exclusive outcome - $O_1, O_2, O_3, \dots$

### Arbitrage Opportunities

- Simultaneously buying and selling across markets for risk-free profit
- Has the effect of aligning markets - removes inefficiencies
- e.g.  a prediction market has two binary futures
	- One trading at $£0.60$, one at $£0.30$ - both will pay out $£1.00$
	- Then buying both guarantees a profit of $£0.1$
- Buying both will raise the price of both - eventually both will equilibriate at $£1$
- Arbitrage aligns the market (the signal is "arbed" away)

## Crowdsourcing

- Enlisting a crowd of human to help solve a problem defined by the system owners
- e.g. collaboratively building software, reviewing a product, executing a small part of a large task
- Can be explicit or implicit - e.g. Google Ad experiments are crowdsourcing but users don't know they're part of an A/B test
- Helpful for tasks that are difficult for a computer to perform
- Examples include Amazon's Mechanical Turk, reCaptcha, Zooniverse
- Getting people involved - can offer money, gamification, appeal to people's send of doing something useful etc.

## Crowdfunding

- e.g. Kickstarter, GoFundMe etc.
- Alternative way to get investment
- Many popular examples e.g. oculus rift

### P2P Lending

- Traditionally had to go to a bank for borrowing money
- Borrowing rates are very high
- The idea with P2P lending is to cut out the banks, and match up lenders with borrowers
- Can then charge lower interest rates, and a higher return for the lender
- Allows borrowers to borrow when banks etc. may refuse them
- Allows lenders to diversify portfolio  to reduce risk
- Light regulation - now regulated by FCA, but not covered by FSCS
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MTEwOTMzOTYsMTc5MzgyNTYxMiwtMT
AwODczNTc3NSw0MTE2NDExMDMsMTE2MDUzOTQ4NywxOTUyMzIx
MDgzLDIxMzkwMzAxODEsLTE4NzA1Nzk5NTcsMTMzODY0ODg4MS
wtMTE1NTQ3MTIyNywxMTMyMTA2OTY3LDczMDk5ODExNl19
-->