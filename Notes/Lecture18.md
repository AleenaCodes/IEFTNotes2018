# Lecture 18 - 4/12/18

## The Evolution of Payment

- Payment started with barter e.g. trading food
- Became complicated - needed an intermediate token of worth - money
- People created coinage from things that are rare e.g. island nations traded for shells, lots of countries used metals
- Goldsmiths formed banks - would look after coins, would verify if a coin was real, issue 'bearer bonds' - essentially ownership of the wealth deposited at the bank
- Banks kept records and would sometimes need to borrow from each other, so this lead to a centralised bank - a ledger of what each bank held (each bank held their own records as well)

![enter image description here](https://lh3.googleusercontent.com/skKvotME1W6IPOHqHndLQvhWwUlhZ1dVdr804O-8S8-fTMxnHW0DKnNrJUfi5TtInmyJotGp9fjO)
Intermediaries between buyers and sellers mean transaction costs, and there is a risk that the intermediaries try to make money by imposing penalties on the seller when transaction go bad for whatever the reason - technical issues, clerical error, fraud etc.

Centralised banks expose customers to risk (e.g. Northern Rock issue in 2007) and this lead to the government nationalising banking

## Blockchain

- Bitcoin peaked a lot last year, but the Bank of England estimates that only 20k people in the UK use Bitcoin
	- It's estimated that around £60m Bitcoin is in circulation, with around 300 transactions per day

### Transaction Example

- Amelia has earned some Bitcoin by doing some coding
- She wants to use some of it to buy a car from Bea
- The transaction will have the following steps
	- Agree the transaction
		- Agree the worth and convert that into Bitcoin
		- Amelia will add a small 'fee' to her payment so that it's likely to be processed more quickly (although this is optional)
	- Create the transaction message
		- The message has 3 components
			- A reference to the earlier transaction that paid Amelia the earned Bitcoin
			- A list of addresses of recipients for the payment (e.g. both Bea and Amelia's addresses so that Amelia will receive the change)
			- A list of amounts to pay to the addresses (the transaction outputs)
		- Amelia will split her Bitcoin between two addresses - Bea's for the car and the rest back to her
		- The fee is specified as well
	- Sign the transaction message
		- Encrypted using her private key - everyone else can use Amelia's public key to confirm that she signed it, but no-one can encrypt a message like she has
	- Broadcast the transaction message
		- Amelia will broadcast the encrypted message and her public key out
		- She spreads her message out to her immediate peers
		- Before broadcasting to their peers, they verify the message by checking it meets constraints ($\text{inputs} \ge \text{outputs}$, all references exist in the Blockchain etc.)
		- At this point the transaction is one of the number of transactions in the network that isn't yet included in the Blockchain
	- Verify the transaction message
		- There are miners in the network who will dedicate their compute power to gain the processing fee
		- Miners compete to be the first to "mine" a "block" containing transaction that haven't yet been added to the Blockchain
		- The mining also adds some new Bitcoin to the network - this is capped so won't happen forever
		- Miners have to show "proof of work" to keep the Blockchain consistent and reliable
	- Success!

### Blocks and Nonce Values

- Each block in the Blockchain has a "header", formed of
	- Timestamp and version number
	- A hash of the previous block header
	- A merkle root summarising the new transactions
	- A nonce value chosen by the miner such that when the header is hashed using $\text{SHA256}^2$ the resulting 256-bit hash has at least $x$ leading 0's
- After the header is a list of transactions that are recorded by the block, including the transactions that pays the miner their fee

Hashing -

- In order to get the work done, we call a cryptographic hashing function twice - to get a double-hashed answer - this is $\text{SHA256}^2$
- The nonce value is a value chosen by the miner, such that when you add it to the header, the resulting hash has at least $x$ leading 0's

#### Hashing Example

- Call initial data $D$, call string of results $S$
- So if you wanted SHA256 to hash $D$ into the binary string $0000\dots11$ you could add an arbitrary "nonce" value to the end of $D$ and keep changing this until $\text{SHA256}^2$ gives you $S$ that evaluates to $3$
	- This would take a very long time
	- It would be quicker to find a nonce that gave $S<2^{200}$ for example
- So a threshold is chosen for the hash as to how many leading 0's there should be
- Checking whether a nonce works is thus very quick - it is either smaller than a given value or not
- But finding a nonce is slow and there's no trick, it always requires brute force

### Verifying a Transaction

![enter image description here](https://lh3.googleusercontent.com/npzy9QPUnNXRuuBg0UVehCbcMZWQBlfC9112lUqPrlVjzDaK2aQ_Q1v7Y99XD92R6UQB8hZzHq9L)
- A transaction is verified by many miners trying nonce values and checking if their correct until someone hits on a correct one
- When a miner $M$ has mined a block with the transaction
	- $M$ gets some new Bitcoin, and also the transaction fees
	- $M$ broadcasts the new block to the network
	- Nodes all add the new block to their copies of the Blockchain
- Miners then start work on the next block

### Double-Spending/Fork

- Digital things tend to be able to be shared multiple times (e.g. a digital song) - so what is to stop someone from spending a Bitcoin multiple times?
- This doesn't happen on the Blockchain
	- A single agreed history of every transaction is stored
	- Nodes check to see if there is enough Bitcoin for a transaction - if not then the transaction isn't included in the block being mined
	- If a coin is spent simultaneously on different parts of the network, a "fork" can occur temporarily
	- The Blockchain will identify and correct a fork quickly without needing centralised adjudication - however it's possible to corrupt the Blockchain if you own $>50\%$ of the network

## Decentralised Ledgers

- Many banks and companies are interested in the use of Blockchain without cryptocurrency
- It presents a way to maintain consensus, have many parallel agents, work without a central bottleneck
- Notable examples include
	- R3 - using Blockchain for recording and auditing inter-bank transaction
	- Land registry in Hondurs by Factcom
	- Stock exchange trades at NASDAQ
	- Diamond registry at Everledger

## Concerns with Bitcoins

- Private keys can still be lost just like a wallet
- It's not anonymous - can still be traced by ISP's
- Vulnerable to Sybil attacks and DoS attacks
- It consumes a huge amount of energy
- There are a lot of illegal transactions in Bitcoin - the reputation is poor
- The whole system could be wipes by an electromagnetic pulse
- Exchange/value total collapse is possible
- Future behaviour of owners is unpredictable - both miners and users

> Some recommended reading - [Izabella Kaminska](https://twitter.com/izakaminska) and [Nouriel Roubini](https://twitter.com/Nouriel), especially his Guardian [article](https://www.theguardian.com/technology/2018/oct/15/blockchain-democracy-decentralisation-bitcoin-price-cryptocurrencies)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg3MjMxMDUxNCw3NDUxOTg1MzIsNjMwND
EzOTgwLDEyMTM2OTk0NzQsLTc1NzQyODEwMSwxNTMwNjg4NTk1
LC0xMjI2MTU1NTUsLTE4ODMxODA5MDEsNzMwOTk4MTE2XX0=
-->