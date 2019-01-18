# Lecture 20 - 11/12/18

## Cybercrime

- Cybercrime/cybersecurity are forms of economic activity
- It's hard to get figures as criminals don't really file tax returns! But it is big business
- Criminals can make a lot of money, and it can take a lot of money to clean up after a hack
- There is little to no regulation on cybercrime

> Book recommendations - Blackhatonomics, The Economic Geographies of Organised Crime

## Economics

- PC/server security has a significant market - many billions
- These companies make legitimate profits from combatting computer crime particularly for OS issues
- Different attacks have different benefits/losses to the parties involved
	- If X attacks Y with DoS, Y loses revenue
	- If X attacks Y with a virus/worm, Y pays for cleanup
	- If X phishes passwords from Y, X can steal money/data from Y
	- If X zombies Y's PC into a botnet, Y's PC works for X

## Terminology

- Virus - program that copies itself via attachment to "host" code - when the host code is moved by a user the virus moves with it
- Worm - a self-replicating program that needs no host or user intervention
- Trojan - malware that masquerades as something else and invites the user to run it
- Rootkit - malware that gives a malicious external actor root-level access to a machine
- Backdoor - a route into a system that bypasses security measures
- Zombie - a machine controlled via backdoor/rootkit techniques
- Botnet - a network of several zombies, controlled as one distributed facility
- Ransomware - malware that encrypts your hard disk and asks a ransom to decrypt it, often asks for crypto as payment for anonymity
- Phishing - fake emails that pretend to come from a trusted source
- Whitehat - malware/attack developed for beningn purposes i.e. to help a company's security

## Prominent Attacks

- 1987 - Christmas Tree - spread via email - paralyses many major networks
- 1989 - Morris Worm - first widespread internet release - buffer overrun
- 2000 - ILoveYou work - affected ~10% of machines on the internet, spread via emails
- 2001 - CodeRed I and II - buffer overrun that sat dormant then attacked hundreds of thousands of hosts, including the White House
- 2001 - Nimda - used backdoors left from CodeRed but ran the attack many times faster than CodeRed - start of the term 'zero day' - taking down an entire network
- 2004 - Sasser - buffer overflow - we can see that this type of attack is still going many years on
- 2004 - Witty - attacked antivirus software, considered 'HIV of software"
- 2006 - Oomp-A - first MacOS virus
- 2007 - Storm Work - formed Storm botnet - 1.7 million infected machines, used to send spam for payment
- 2008 - Stormf**cker - started a fight to take over the Storm botnet
	- Competition between Storm and rival botnet Nugache resulted in a price-war for spam distribution
- 2009 - Conficker - largest infection since SQLSlammer - 9-15 million machines including lots of government systems
- 2009 - Zeus - a keylogger botnet, 3.6 million+ machine
- 2010 - PGPCoder - ransomware
- 2016 - Mirai - botnet, first IOT large-scale attack, disrupted Twitter, Spotify, Paypal etc.
- 2017 - Wannacry - ransomware that hit NHS, cost £100million+ - exposed that malware was a way to genuinely take lives
- Stuxnet was developed by the US/Israel to target nuclear weapons production, accidentally leaked and many offshoots deployed - Duqu (2011), Flame (2012), Triton(2017)

## HP Virus Throttle

- Twycross and Williamson worked in HP Labs in 2003
- The idea was to monitor when machines were infected and allow the device to continue running but slow-down
- There were 3 key innovations in this
	- Focussed on network behaviour of the virus (e.g. lots of connections per second)
	- Doesn't stop mobile code from entering, but stops from leaving the system
	- Outgoing connections are delayed instead of dropped - robust to false positives
- Possible to be defeated but overall a decent solution

> pick up on slide 33
> https://www.ole.bris.ac.uk/bbcswebdav/pid-3602430-dt-content-rid-10468874_2/courses/COMSM0019_2018/open_access_cs/lecture_slides/COMSM0019_18_20.Malware.pdf

## Vulnerabilities Market

- Security companies would spot vulnerabilities and disclose them publically
	- They argued this would force software companies to improve security
- There was then a move to 'responsible disclosure' - telling the software company before publically disclosing it to give them a headstart in developing patches
- Software vulnerabilities have a value -
	- 'Black hat' hackers can gain direct economic benefit
	- Software companies can make their software more securt
	- Security agnecies can conduct surveillance and cyber-warfare
- An informal marketplace has developed -
	- Companies identify vulnerabilities and sell them to the highest bidder
	- There are small specialist companies, and large defense contractors

## Open Problems in Security-Economics

- Algorithmic Mechanism Design
	- Network protocols and interfaces should be designed to be strategy-proof
- Psychology and Security
	- Many things are insecure because of humans co-operating inappropriately
- Network Topology and Information Security
	- Different topologies have different robustness properties
	- Need to better understand the functional topology of technology networks
- Large Project Management
	- Large IT system project failures can cost billions and threaten whole organisations
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU3MDY1MDY1OCwtNzA3ODM4ODUwLDE1Nz
g1NjUyNTAsLTM2MDYwNDk0NiwtMjEzOTI4NTcyNyw4Mjk5OTA5
MTgsMTEzNDc3NTUxNiw2NzgwNDE4NjMsLTM5MTQxOTU1LDIwOT
Q3Nzk2ODksNTcxNjEyNjE2LDczMDk5ODExNl19
-->