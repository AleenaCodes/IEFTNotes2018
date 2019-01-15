# Lecture 12 - 6/11/18

## Intro

- All we've learnt so far about making money is 'buy low, sell high'
- But this doesn't work well in markets that are static, horizontal or falling
- This lecture will look at making money when prices are falling, not changing much or changing unpredictably

## Short-Sellings

Terminology

- To go long $X$ - to buy $X$, expecting the price to rise (a "bullish" position)
- To go short $X$ - to sell $X$, expecting the price to fall (a "bearish" position)
- Can be abbreviated e.g. "I'm short IBM"

However there is a way of making money when prices are falling - short-selling - making money by trading the asset as the price is going down

Short-selling

- Borrow $n * XYZ$ from a lender
- Sell $n * XYZ$ now (time = $t_1$) at price $P_1$
- Price of $XYZ$ falls to $P_2$
- At time = $t_2$, buy $n * XYZ$ at $P_2$ and return to lender
- Profit = $n * (P_1 - P_2) - \text{LenderFee} - \text{costs}$

## Derivative Contracts

This is formalised in a market for derivatives - a *derivative* is a contract between a buyer a seller, which derives it's value from the changing value of another asset

- The asset is known as the "underlying"
- There are lots of types of derivatives - swaps, futures, options

Two key types of derivatives ares futures and options - both of these are standardised and exchange-traded, they can be traded just like a good

A *future* is a contract that **will*** be executed by/on a set delivery date

- Futures contracts are required to be executed/exercised
- When a contract is issued, it specifies a "forward price"
- On the delivery, the contract is executed at the forward
- The buyer of the foward are in the long position, the seller is in the short position

An *option* is a contract that **may** be executed by/on the expiry date

- Options contracts confer the right (but not obligation) to exercise
- An option specifies a "strike price" aka the "exercise price"
- Options to sell are "puts" and options to buy are "calls"

### Options

- One options contract is the right to buy/sell 100 shares
- The price of an option depends on the price of the underlying (which can change over time), and some notion of risk
- The "strike price" is the price at which you can buy/sell the underlying on exercise
- "Expiry" is the last date on which you can exercise an option
	- American-style - exercise can happen on any date up to expiry
	- European-style - exercise can happen only on the expiry date (at "maturity")
- An option is written/issued by its seller, and help/exercise by its buyer
- The option price is determined by
	- Intrinsic - money received if the option is exercised now
	- Volatility - premium depends on the underlying's price volatility
	- Time value - potential risk-free return on money saved with regards to buying the underlying

The maths of option-pricing is complicated - the Black-Scholes pricing model is used

#### Calls vs Puts

|Calls|Puts|
|:--|:--|
|Right to buy $N$ units of underlying|Right to sell $N$ units of underlying|
|Option-holder can buy at strike price|Option-holder can sell at strike price|
|If exercised, the option-writer (seller) must sell shares at strike price|If exercised, the option-holder (buyer) must buy shares at strike price|
|In-the-money (ITM) - $\text{underlying price} > \text{strike price}$|In-the-money (ITM) - $\text{underlying price} < \text{strike price}$|
|Out-of-the-money (OTM, "underwater") - $\text{underlying price} < \text{strike price}$|Out-of-the-money (OTM, "underwater") - $\text{underlying price} > \text{strike price}$|
|At-the-money - $\text{underlying price} = \text{strike price}$|At-the-money - $\text{underlying price} = \text{strike price}$|

Different tactics can be used to make money from any market scenario

![enter image description here](https://lh3.googleusercontent.com/8YTgTdwkB_iQlzfIea7vOBuupdJ4xUgCQCJF0BtfrDTKb4DbxcHd98yvRydaPr_mVxK7n8_uMAvE)
Isn't this just gambling? Yeah, but seen as sophisticated instead!

## Betting Exchanges

- Betting exchanges are electronic marketplaces where gamblers interact to find someone to take the opposite side of their bet (either buy/"back" or sell/"lay")
- They are different to bookmakers, where a customer backs the event and the bookie lays the bet
- At a betting exchange -
	- All customers can either back or lay
	- Buys and sells are displayed in a manner similar to the LOB
	- Customers can trade bets 'in play' - i.e. while an event is happening
- Traditional bookmakers have argued that allowing anonymous customers to lay events encourages corruption - it's easier to throw a race than to win it
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzI5NjIzODk1LDExNzc1NjAzNTIsMTE5MD
MzODksLTE5OTA2NjM4NzEsMjEwOTkzNzQxMiwtMTc1NDQ0OTA5
MywxNDM3MjAyOTExLDExMDg0NTA3NTIsNDA1MTU3MTg0LC0xND
kyNjUyOTkyLDE5NDMxNTgzNDcsMTEyODc3MDA2OSw2MzM2OTQ2
MzEsLTExMTg0MjI2MjYsNzMwOTk4MTE2XX0=
-->