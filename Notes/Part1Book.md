# Notes on Part 1 of The Economics of Information technology

> This book is from 2001 so is actually incredibly dated, nevertheless the notes below cover what the book says

## Intellectual property

Copyright law defines the property rights of the product being sold

Patent law defines the conditions that affect the incentives for, and constraints on, innovation on physical devices and software processes.

## Internet boom

The internet boom of the 1990s can be interpreted as an instance of "combinatorial innovation" - the technology provided a rich set of components that could be combined and recombined to make new products.

Other examples of this include the standardisation of mechanical parts in the early 19th century, and the creation of the gas engine. Both of these sparked waves of combinatorial innovation. Schumpeter (2000) points out that combinatorial innovation is one of the reasons that innovation appears in "waves". He emphasises a "demand-side" explanation for this, but a complementary "supply-side" explanation can also be considered - when many people work with the same components it's common to see the same invention made independently (e.g. with electric lights, the airplane, the telephone etc.)

A third explanation for waves of innovation is the development of components - as I've product takes off, so do other complementary products (e.g roads from bicycle usage, and gasoline from stationary farm engines resulted in automobiles having an infrastructure in place, so they were able to gain in popularity. This is an example of the "indirect network effect".

Technological revolutions such as cars, integrated circuits, servers etc. took many years, or even decades, to develop - so how did the internet revolution take off in only a few years? Some possible explanations -

- It's minor compared to other revolutions
- The "components" aren't physical so much as virtual - ideas, protocols, software etc. So no problems with manufacturing or procuring supplies - things could be distributed very quickly

It should also be noted that open-source software lower the back to innovation greatly.

### Financial Speculation

Each period of combinatorial innovation are accompanied by financial speculation - new technologies inevitably lead to an investment boom.

The period closest to the internet boom is probably the "Euphoria of 1923" - centered around broadcast radio. Like other innovations, it resulted in a lot of "dumb money" coming into the stock market and so it set off a stock market bubble.

Billions of dollars were lost in the internet bubble, but a substantial fraction of investment in that period still has social value. The biggest capital investment during the bubble years was in the generation of young adults who engaged and learnt about tech - this is the thing that's likely to have the most pay-off in the long-term.

### Where are we now?

An abundance of everything has now been produced - computer cycles, bandwidth etc. but the challenge now is to understand how to use the capital investment of the 90's to improve the way goods and services are produced.

### The New Economy

Some people argue that a new economics is needed to understand the new 'economy of bits' but it seems unnecessary - the old economics works just fine, but the different effects are just more common - the network effect, switching costs etc.

## Differentiation of product and price

Price discrimination is important in high-tech industries for two reasons -

- High-fixed-cost, low-marginal-cost technologies are common, leading to significant market power
- Tech allows for fine-grained observation and analysis of consumer behaviour, meaning price discrimination can be done on a very personalised level


### 1st Degree Price Discrimination

In the extreme case, information technology effectively reduces this down to a 'market of 1', and this is likely to continue as companies gather data to offer highly customised products.

Ulph and Vulkan (2000) observed two effects -

- "Enhanced surplus extraction" - personalised pricing allowed firms to charge prices closer to the customer's reservation price
- "Intensified competition" - each consumer is a market to be tested
  - When consumer tastes are not dramatically different, the intensified competition effect dominates the enhanced surplus extraction effect, making firms worse off and consumers better off

However their research assumes full knowledge, whereas in reality long-term suppliers would know more about customers than new ones.

Personalised pricing also raises privacy issues

### 2nd Degree Price Discrimination

This involves "versioning" - where all consumers receive the same set of options. This was common in products before technological ones, but information technology is helpful in collecting information to design the different versions.

### 3rd Degree Price Discrimination

This is selling at different prices to different groups - classic price discrimination.

Armstrong and Vickers (2001) observed that when consumers have the same taste, then competitive 3rd degree price discrimination will make consumers better off - the competition forces firms to maximise consumer utility, and price discrimination gives them flexibility to deal with the fixed cost.

Where there is no fixed cost, consumer utility falls with competitive 3rd degree price discrimination, although overall welfare (consumer + producer surplus) still rises.

With heterogeneous consumers the situation is less clear-cut - but generally consumer surplus is reduced and profits are enhanced by competitive price discrimination, so welfare may fall easily.

### Conditioning on Purchase History

Another form of price discrimination is discriminating based on purchase history - this is especially interesting in high-tech markets as there is a lot more data for firms to go on.

Tactics include offering enhancements to older customers, and lowballing prices to steal customers from other firms - a "duopoly" model.

Acquisti and Varian (2001) found that in a market of high-value and low-value consumers, it was not profitable for a monopolistic seller to make offers based on purchase history. But they also found that if the monopolist can offer an enhanced service, it may be optimal to condition prices on earlier behaviour and extract some value from this enhanced service.

Even in a competitive environment, a seller may have a partial monopoly in providing personalised services such as recommendations, and this exhibits a form of lock-in for the consumer.

### Search

The Internet has lowered the cost of searching dramatically, and it seems that consumers do a lot of information gathering online before a purchase, even in industries with relatively few direct online transactions.

There has been a lot of research around what happens when some consumers use price comparison sites, and others shop at random. The solution for sellers is to use a mixed strategy and randomise the prices they charge. This allows them to sometimes charge low prices to compete for searchers, but on average still charge a high price to non-searchers.

### Bundling

Bundling is the practice of selling two or more distinctive goods for a single price.  This is particularly attractive for information goods, since the marginal cost of adding an extra good to a bundle is negligible.

Two distinct economic effects are observed with this

- Reduced dispersion of willingness to pay
  - Essentially makes the demand curve flatter
- Increased barrier to entry
  - The attractive customers across multiple products are already taken so it's harder for a competitor to enter the market

## Switching Costs and Lock-In

Switching costs are endemic in high-tech industries, so switching suppliers is virtually unthinkable - customers are locked in.

Klemperer (1995) concluded that switching costs are generally bad for consumer welfare as they typically raise prices over the lifetime of the product.

### Switching Cost and Price Discrimination

A common example of switching costs is printers - cheap printers with expensive ink. The market is competitive *ex ante*, but since ink is incompatible, it is monopolised *ex post*

This situation can be viewed as a form of price discrimination -

- The consumer cares about the price of the printer plus the price of the amount of cartridges they buy
- If all consumers are identical, a monopolist that commits to future prices would set the price of the cartridges equal to their marginal cost, and use its monopoly power on the printer

Suppose there are two types of customers - high-demand and low-demand customers.

Let

- $p$ be the price of cartridges
- $c$ be their marginal cost
- $x_H(p)$ be the demand function of the high-demand type
- $x_L(p)$ be the demand function of the low-demand type

The the profit maximisation problem for the monopolist is

$$\max_p 2v_L(p) + (p-c)[x_H(p) + x_L(p)]$$

Recalling that $v_L\prime(p) = -x_L(p)$ we can write the first-order conditions as

$$p-c = \frac{x_L(p)-x_H(p)}{x_L\prime(p)+x_H\prime(p)}$$

Hence the greater the gap between the high demand and low demand, the larger the price-cost margin.

Here, the user distinguish their type by the amount of their usage, so the seller can price discriminate by building in a positive price-cost margin on the usage, rather than the initial purchase price.

## Supply Side Economies of Scale

Many tech related businesses have cost structures with large fixed costs and small, even zero, marginal costs - they are "natural monopolies"

There is not necessarily a social loss from this -

- Competition in the real-world is more dynamic than in theory - monopolies don't just come about by themselves
- If the biggest firm has the biggest cost advantage, then firms will all compete to by the biggest, and consumers will benefit from the competition.
- Information technology has reduce the fixed costs, and thus the minimum efficient scale of operation in many markets - it makes it more possible for firms to overcome cost advantages bia leapfrogging
  - Christensen (1997) emphasised the role of "disruptive technologies" - low-cost and initially low-quality innovations that unseate established industry players.
- PC's are technologically obsolete before they are functionally obselete - the installed base creates competition for suppliers, as they have to continually convince users to upgrade
  - Coase (1972) called this the "durable goods monopoly"
- Since the cost of and information to the end user depends on  the sum of the prices of components, each component maker wants to see low prices from other components - hardware makers want cheap software and vice versa

Although supply-side economies of scale may lead to more concentrated industries, this may not be so bad for consumers - price discipline assets itself through different routes -

- Competition to acquire monopoly
  - This forces lower prices for consumers
  - This may also produce inefficient rent dissipation though
- Reduction in fixed costs
  - IT reduces fixed costs over time, allowing more market entrants
  - This is fertile ground for competition and disruptive technologies
- Competition with your prior production
  - Often the installed base of a firm's product is a formidable competitor
- Pressure from complementors
  - Sellers of complementary products want lower system prices and have various ways to exert pressures to accomplish this

### Competition and Welfare

The traditional view of a monopoly is that it creates deadweight loss and producer surplus. However, perfect price discrimination eliminates the deadweight loss, and competition for the monopoly transfers the resulting monopoly rents to the consumers.

The theorems of welfare economics assert -

- A competitive equilibrium is Pareto efficient (1)
- Under certain convexity assumptions, every Pareto efficient outcome can be supported as a competitive equilibrium (2)

However, these are both irrelevant under the high fixed cost and low marginal cost conditions

Instead we have two more theorems of welfare economics -

- A perfectly discriminating monopolist can capture all surplus for itself and hence produce a Pareto efficient output (3)
- Competition among perfectly discriminating monopolists will transfer this surplus to consumers - yielding the same outcome as pure competition (4)

### Competing for Monopoly

(4) Assumes that the competition for the monopoly rent necessarily benefits consumers. If the strategic variables for firms are prices then this is true, and other things such as innovation, quality etc. also tend to benefit consumers.

But firms can also compete on other dimensions such as political lobbying, accumulation of excess capacity, and premature entry.

The reality is that there are many dimensions to competition, some of which transfer payments to consumers (e.g. price), and some of which transfers to third parties (e.g. bribes) and some of which involve pure rent dissipation (such as investment in capacity that is never used).

Competition is generally a good thing, but some regulations may be required to make sure that competition takes socially beneficial forms.

It can be useful to think of the monopoly as a prize to be auctioned off, and so different auction forms describe different forms of competition -

- English auction
  - If two makers are bidding to install their system in a company, then the winning bidder still retains some surplus
- Everyone pays auction
  - Such as a parent race, or a race to build scale
  - Let $v_1$ and $v_2$ be the value of the prizes to players 1 and 2
    - When the players are symmetric ($v_1 = v_2$) then the sum of payments by the player equals the expected value of the prize
    - But when $v_1 \ne v_2$ the player with the highest value always bids but the player with the second-highest value will bid with the probability $\frac{v_2}{v_1}$ and so if $v_2$ is relatively small then the equilibrium payment approaches $\frac{v_2}{2}$ - half the payment in an English auction
    - This difference is because the player with a low value for the monopoly often doesn't bid at all so the player with a high value often shaves their bid - which results in consumers up with less surplus
- War of attrition
  - Both players compete until one drops out
  - However if the value for the monopoly is much greater for one player than the other, then the other one may drop out at the start, so consumers will not benefit from competition


The lessen from looking at these is that if all parties have to pay to compete, then there will be less competition, and less benefit passed to the consumer. Hence an auction where only the winner pays is much better from a social point of view.

It is also worth noting that in some conditions, the competition to acquire a price discriminating monopoly will dissipate all rents. If this dissipation involves offering heavy discounts to consumers, then the gain in surplus that consumers receive in the competition phase may offset the losses incurred in the monopoly phase.

## Demand-Side Economics of Scale

Demand-side economics of scale, are known as "network externalities", or "network effects", since they commonly occurs in network industries.

A good exhibits network effects, if the demand for the good depends on how many other people purchase it, e.g. a fax machine.

There are two types of network effects

- Direct network effects - the value comes from other people having the product e.g. fax machines
- Indirect network effects - the value of your product will be increased by others having it indirectly e.g. others having broadband will mean better infrastructure and speed for you

With supply-side economics, average cost decreases with sale, while with demand-side economics of scale, average revenue (demand) increases with scale.

When network effects are present, there are normally multiple equilibria

- No-one adopts the network so it has no value
- If there are enough adopters then the good becomes more values so more adopt it - positive feedback
  - The demand curve will be a hump shape - as the willingness to pay increases with adopters, then decreases once only consumers with less willingness to pay are left


![](https://lh3.googleusercontent.com/6Wd4hA06o31hJuW5L9iry3xi8mf9iYuabHZn9Xpr7PBVL-tU40EAJYXvzZYjGAqbycLvoSpExT6n)

There are 3 equilibria here - with the middle equilibrium showing 'critical mass' - if a product can get above this, the positive feedback kicks in.

Early adopters may also value the network good less than subsequent adopters, so it makes sense for sellers to offer them at a lower price - 'penetration pricing'.

## Standards

If the value of a network depends on its size, then interconnection/standardisation becomes an important strategic decision.

Generally, dominant firms with established networks prefer not to interconnect, but it's not always anathema to dominant firms and the benefits can be worth it - consider that

$\text{your value} = \text{your share} \times \text{total industry value}$

So when total industry value depends on the size of the market, adopting a standard may increase total value so much that it overcomes the possible dilution in market share.

There are three forms of competition in a standards setting -

- Standards war - firms compete to determine the standard
- Standards negotiation - firms want a standard but disagree on what it should be
- Standards leader - one firms leads with a standard, the other firm wants to interoperate with the existing standard

There are also considerable cost savings in standardisation, due to economies of scale in manufacture and risk reduction.

### Standards War

There are common tactics in a standards war -

- Penetration pricing to build an early lead
- Building alliances with suppliers of complementary products
- Expectations management e.g. bragging about market share
- Commitments to lower prices in the future

### Standard Negotiation

Each players prefers a standard to no standard, but prefers their own standard to the other's.

The outcome depends on the threat point - the payoff the parties receive if negotiations break down. The better off the bargainer is the more concession they can extract from their counterpart, so companies often develop proprietary solutions while engaged in negotiations, and it's not uncommon for companies to fail to disclose all relevant information in negotiations, thus leading to lawsuits etc.

Sometimes standards are negotiated under the oversight of official bodies, but while they have the advantage of experience, they can also be very slow-moving.

### Standards Leader

In a market where an established firm wants to maintain a proprietary standard but a smaller firm wants to interconnect, there are several tactics

- The proprietary standard may be protected by IP laws
- The leader may change its technology frequently to keep the followers behind
  - This also helps to resolve the 'durable good monopoly' issue for them as well
- The follow can use an adapter, either with or without the larger firm's co-operation

## System Effects

It's common in high-tech industries to see products that are useless unless combined with other products - e.g. hardware is useless without software, DVD players without DVDs etc. These are "complements" - good whose value depend on their being used together.

Lock-in often occurs because users must invest in complementary products to use a good.

Direct network effects as a symmetric form of complementaries, and indirect network effects are also a form of system effects.

Standards involve a form of complementarity in that they are often designed to allow for seamless interconnection of components. However systems of complements raise economic issues - who will do the integration, the manufacturer, end user or some intermediary?

Cournout (1838) analysed the stategic interactions between producers of complementary products - zinc and copper (as many companies bought from both of them to combine the two). He looked at what would happen is the two suppliers combined.

Assume that $1$ unit of copper and $1$ unit of zinc combine to form $1$ unit of brass. Competition will push the price of brass down to its cost, which will be the sum of the prices. So demand of brass will be

$D(p_1 + p_2)$

Assuming the cost of production is zero for simplicity, the two producers want to maximise the profit of producing their metal.

Copper: $\max\limits_{p_1}  \ p_1 D(p_1 + p_2)$
Zinc: $\max\limits_{p_2}  \ p_2 D(p_1 + p_2)$

If the two complementary monopolists merged, they would solve the joint profit maximisation problem

$\max\limits_{p_1, p_2} \ (p_1 + p_2) D(p_1 + p_2)$

Cournot showed that the complementary monopolists would set prices that were higher than if they merged. This is intuitive if we think of how if the price of zinc was cheaper then brass producers would buy more zinc as well, but how this is only profitable when the two producers are merged.

There are many ways a firm may induce a complementor to cut its price -

- Integrate
  - One complementor acquires another, forming a merge identity
- Collaborate
  - The firms set up a formula for revenue sharing, then one firm sets the price of the joint system
- Negotiate
  - Two complementary firms may commit to both cutting a price at the same time
- Nurture
  - One firm works with the other to reduce their Costs
- Commoditise
  - One firm attempts to stimulate competition in the other's market, thereby pushing down prices

## Computer Mediated Transactions

More and more transactions are being mediated by computers these days, and this allows for new types of data mining and revenue models.

For example Blockbuster were able to use a model where studios would receive part of the revenue from DVD rentals, which was achievable using recording technology inside the registers.

Another example is in the trucking industry - which uses technology to record speed, when the engine is idling or accelerating, and many other details. These are then used for coordination and also fraud detection.
