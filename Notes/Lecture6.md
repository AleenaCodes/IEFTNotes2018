# Lecture 6 - 16/10/18

## Auctions

- Often used for things like artwork
- Provide a mechanism to allow buyers and sellers to meet and trade
- One item and multiple potential buyers

There are several common auctions

- English Auction - Open ascending price acution
	- Everyone can see other bids
	- Price rises over time
	- Bidders continue bidding until no-one wants to raise their bid
	- Highest bid wins and pats that price
- Dutch Auction - Open descending price auction
	- Everyone can see other bids
	- Price lowers over time
	- Auctioneer lowers offer until a buyer accepts
	- Buyer pays that price
- Sealed bid auctions
	- All bidders enter bids to auctioneer and the highest bid wins
	- Multiple types
		- First price sealed acution - winner pays the price they bid
		- Second price sealed auction (Vickrey) - winner pays the second-highest price
- Continuous double auction (CDA)
	- Buyers and sellers can enter a bid/offer at any time
	- Commonly used in financial markets

### Incentive Compatibility

- An auction is incentive compatible if it encourages bidders to bid their true value of the good
- An English auction is incentive compatible - the bidder keeps bidding until they win, or something else bids more than they're willing to pay
- A Dutch auction isn't incentive compatible - the bidder tries to guess what others value the good at, and attempts to stop the auction before that price
- A first-price sealed bid auction isn't incentive compatible - the bidder wants to bid less than they value the good at, based on what they believe others value it as
- A Vickrey auction is incentive compatible - the bidder can safely bid their true valuation, knowing it won't affect the price they pay if they win

### Equivalence of Auctions

- If you have a private value for the good, then English and Vickrey auctions are almost equivalent
- Under certain conditions, Dutch and First Price bids are also equivalent in terms of closing price
- But bidders are not always rational, there's lots of psychological factors

### eBay auctions

- Auctions but with a time limit
- End point changes the behaviour of people in the auction
	- Lots of people wait until the end of the auction to make their bid
	- 'Sniping' - lots of tools to do this as well

Solutions to sniping -

- Extend the deadline whenever a bid is placed - turns it into an English auction
- Get everyone to use a sniper - eBay did this - allows 'proxy' bidding so people effectively bid their highest value - essentially turns it into a Vickey auction

### Reverse Auctions

- Suppliers bid to meet a contract
- Often suppliers must be 'qualified' - hence less open than eBay
- A more formalised version of 'Request for Quotes'
- Sometimes found to be too rigid

## Google Ad Auctions

- Largest number of auctions in the world
	- Billions per week
- 11 slots are auctioned, with up to 3 premium slots above a search
- Google assigns them based on Bid Price * Quality
	- Quality is dependent on click-through, relevancy, landing page quality and load speed

Google ad auctions are sealed bid second price

- Google first started with a first-pruce auction
- But they realised that bidders would load the servers to work out the minimum price they could pay
- They wanted the auction to be incentive compatible to reduce monitoring overhead

### Quality

- Quality $q$ is an estimate of probability of being clicked
- Google considers the big to be $(p*q)$
- The bidder below them i.e. the 'second price' in the auction is $(p' * q')$
- The winning bidder pays $\frac{(p'*q')}{q}$

### Estimating 'Probability of Being Clicked'

- The probability of being clicked is dependent on ad quality and ad placement
- Google needs a model for the latter
	- Randomly allocates adverts to different positions to estimate the position-specific effect
- They offer a similar random-placement service to advertisers to allow them to experiment themselves
- Experiments are cheaper online - Google can easily run many thousands of experiments in a day

### The Effect of Competition

- As the price set depends on the bids of those under you, more competition is beneficial for Google
- To stimulate competition, Google prefers  advertisers use partial match instead of exact match

## Impacts of Internet Economics

- Direct - environmental impact
	- 2.5% of the UK energy emissions
	- Hopes that fast innovation will help reduce this
- Indirect - changes in behaviour that technology use enables
	- Online shopping
	- Remote working
- Systematic - structural changes in society enabled by technology
	- People taking jobs further away - travelling to office less
- Social impacts
	- Employment
	- Internet-facilitated tax avoided
	- Privacy
	- Transparency

### Do these business models stimulate small business?

- Cost of starting a small business has decreased
	- No physical office needed
- Reach of the small business has increased
	- Niche business are therefore more viable
- Gigging
	- Platform technologies leading to gigging workers
	- Many issues around the rights of these giggers

### Internet Facilitated Tax Avoidance

- Tax evasion - illegal non-payment of tax
- Tax avoidance - legal exploitation of loopholes in tax laws
- Tax laws apply to individual companies, but internet companies can easily set up as multi-national
- The internet makes avoidance easier
	- Transactions can take place away from the country of the customer
	- It's easier for an organisation to conduct business in a country while only having 'skeleton staff' there

#### Double Irish Dutch Sandwich

- Irish bread, Dutch filling
- Tax loophole allowing multi-nationals to avoid corporate tax

![irish_dutch_sandwich](https://lh3.googleusercontent.com/ay2rsWcclpoao8BZKa9F1zd_Wz9lBk8u5ldb4-Js5bPex_8KGqALVCVVsAsKpSg1VmlIabEcS9Ca)

- US parent company
- Have an Irish holding company, which is tax resident in Bermuda
	- Exploits Irish rule where tax is paid in company with management
- Have a Dutch holding company
- Have an Irish operational company

<br>

- US company licences the IP to the Irish/Bermudan holding company
- The Irish/Bermudan holding company sublicenses the IP to the Dutch holding company
- The Dutch holding company sublicenses the IP to the Irish operational company

<br>

- The Irish operational company has actual employees
	- Takes business revenue from non-US customers
	- It has to pay tax on the work it's doing
- The Irish operational company pays royalties to the Dutch holding company of an amount equal to the income
	- Hence no profit is made - no tax to pay (as being sent to another EU country)
- The Dutch holding company pays royalty to the Irish/Bermudan holding company of that amount
	- Hence no profit - no tax to pay to Bermuda
- The money ends up in Irish/Bermudan company 
	- Does not have to pay tax as all the money is in Bermuda where there is no tax
- The US company now has all the money sitting in the Irish/Bermudan holding company
	- It can pay royalties/dividends to the US company or invest back into the company
- 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYwNDc5ODYzNiwtMTkzOTU4ODUzMywtMT
Q1OTQ5NDgxNSw0MTE4OTE4NDcsODIzNjA2NDUwLC0xMjc3ODYy
NDUzLDExMDI4MTM3MDcsMTg2NDY2OTgwOCwtNDA2ODY4NDc2LD
I2MzY3MjAwLDE0NzAxNjU1MCwtMTI2NDg4ODU2LDEzODMyNjIw
ODQsLTE3NzcwNjgyMDQsMjExNjYzNTE0MiwxMTMzNzU3MjQ3LD
czMDk5ODExNl19
-->