
# Lecture 10.5 - 30/11/18

From the extra video at https://vimeo.com/307827599

## Intro

- The Limit-Order-Book (LOB) is a data structure that is at the core of most modern financial exchanges

## Results from the In-Class Experiments

![](https://lh3.googleusercontent.com/RGVkZFTjg5670eXHkflmm3Ptf27U1NcZPEGx74N0RKIDl6zcgw8v5YyJPGrTjh0s1KKKEfqnmSqq)
- Time on the x-axis, price on the y-axis
- Each market shows a single transaction
- There were 5 experiments - C to G

Each experiments was as follows

- Experiments C and D are designed so the market's theoretical underlying equilibrium price is 150
- Experiments E and F have an equilibrium price of 500
- Experiment G has an equilibrium price of 150

![](https://lh3.googleusercontent.com/pF0M2KgVxtV9iT9g4escb8PDHOjiXUK_WgkIJ6E0HL--79FHjxJgUhtPM625qTHLwABq1gBly2gZ)
- Highlighting these on the graph, it is clear that the transaction prices cluster around the equilibrium, much like in Smith's experimental work
- Smith introduced an alpha value - root mean square of the deviation around the equilibrium price - as a percentage of that price

The alpha values of the experiments are

- C - 12.5%
- D - 11.5%
- E - 9.8%
- F - .15%
- G - 11.3%

For this we can see that our classroom results were similar to those in Smith's original paper

## BSE

- Real-world markets aren't physical anymore, they're fully electronic - both bids and records
- Many of the markets are highly automated
- There is a lot of demand (and money) for people who can work on algorithmic trading
- The best way for students to play with algorithmic trading is to run it on an exchange - and to save losing a lot of money, the BSE was created
	- It's available on Github!
- Having something like the BSE available is much more realistic to play with than running things on time series' of previous trading periods - as it means the market price will actually change when your transaction is run - as it would in real life

### GUI Example

While BSE doesn't have a GUI, if it did it would look like this

![enter image description here](https://lh3.googleusercontent.com/7d3IVaYAXi0pS3vRRiqAli7ct2xTzHz42NxCswMoui4SfPlBi7jKMkw1H85BGcuU7ee8YwSaH-Es)
- The left-hand side is the LOB
	- There is a bid side (left) and ask side (right)
	- At the top is the best bid and the best ask - so the highest bid, and the lowest ask
	- The quantities of each bid and ask if also displayed next to it
	- The rest of the bids and asks are displayed in 'worsening' order
	- In red is the length of time the market has been open
	- In green is an estimate of the underlying equilibrium price
	- The yellow table shows the most recent order
	- The green bar is the 'tape' - a time series of events in the market - transactions, cancellations of orders etc.
- The right-hand side
	- This takes the LOC and plots it as a graph of supply and demand curves
	- Quantity on the x-axis and price on the y-axis
	- The green cross indicated the micro-price (defined below)
- Two statistics can be calculated
	- The mid-price
		- The bid-offer spread is the different between the top bid and top ask
		- va - vb where:
			- va is the value of the item in the best ask
			- vb is the value of the item in the best bid
		- here 177-150=27
		- The mid-price is the midpoint of the spread
		- (va + vb) / 2
			- va is the value of the item in the best ask
			- vb is the value of the item in the best bid
		- here (177+150)/2 = 163.5
		- The problem is that it takes not notice of the quantities available - we know that a big imbalance in these would shift prices
	- The micro-price
		- This takes quantities into account as well
		- It's calculated by the (qb / qa + qb) * va + (qa / qa + qb) * vb where:
			- qa is the quantity of the item in the best ask
			- qb is the quantity of the item in the best bid
			- va is the value of the item in the best ask
			- vb is the value of the item in the best bid
		- Here it is (5/5+13) * 177 + (13/5+13) * 150 = 157.5
		- By taking quantities into account, the micro-price will be closer to the best bid if there's an excess on the ask side, and vice versa
		- In the GUI picture the number in green is the micro-price
	- We're going to work with the micro-price in this example
- The range of prices in the market is sometimes called the 'price depth'
- The quantity available on both sides of the book is sometimes called the 'volume depth'

> see the full video from 17:02 - 21:05 for a worked example of the BSE in action

Why doesn't BSE have a GUI? -

- It's intended to be run over a long period of time on a very large number of runs
- A GUI would slow things down significantly



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4MTYzMzgyM119
-->
