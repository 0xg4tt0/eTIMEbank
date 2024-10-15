`work in progress`

# Context document for eTIMEbank


#### Contents:
- Introduction
- What is time banking?
- Addressing the 'how do you value one hour' question
- An experiment in new forms of collectively ascribing 'value'
- Why not just use Bitcoin?
- Design choices for project
- Relevant features of Chaumian ecash for time banking
- 3 potential use-cases
  - remote / off-grid cashless communities
  - Volunteer-run events
  - Incentivising pro-social behaviour / public goods
  - Bitcoin Citadels / Journeyman model
- Time Banking resources


## Introduction


Concept is the creation of an ecash based application that runs both the wallet client and mint logic for time-banking communities.

This project by design not include any Bitcoin elements and does not use satoshis as a unit, it is an exercise in applying a Chaumian blinded signatures scheme to the concept of Time Banking. To know more about the design choices, what time banking is, and the reason why I made this project read the rest of this context.md



## What is time banking?

*In economics, a time-based currency is an alternative currency or exchange system where the unit of account is the person-hour or some other time unit. Some time-based currencies value everyone's contributions equally: one hour equals one service credit. In these systems, one person volunteers to work for an hour for another person; thus, they are credited with one hour, which they can redeem for an hour of service from another volunteer.*

*Others use time units that might be fractions of an hour (e.g. minutes, ten minutes – 6 units/hour, or 15 minutes – 4 units/hour). While most time-based exchange systems are service exchanges in that most exchange involves the provision of services that can be measured in a time unit, it is also possible to exchange goods by 'pricing' them in terms of the average national hourly wage rate (e.g. if the average hourly rate is $20/hour, then a commodity valued at $20 in the national currency would be equivalent to 1 hour).*

- [Wikipedia entry introduction:](https://en.wikipedia.org/wiki/Time_banking) 


Time Banking is an alternative currency system with a long history and [active communities that operate with these systems in 2024](https://en.wikipedia.org/wiki/Time-based_currency#Studies_and_examples), it is an alternative to the fiat banking system which uses a unit of account this abstracted from meatspace/reality. 

Similarly to Bitcoin, Time Banking exists in contrasts to the current social consensus that 'time is money' and that a service or product (both of which can be calculated in person-hours) are attributed a numismatic 'value' to it which can be exchange/traded with another party for other services or products, creating an 'economy'

Time Banking presents a unique mental and social model for what an 'economy' can be - where the 'unit of account' is the real-world time that a person contributes to their local community/society/economy - 'time is money, so let us collaborate with minutes and not fiat'

There has been a plethora of research and books that have been written on the concept of Time Banking, this section is just a small introduction and primer for the understanding of why I chose Time Banking as a alternative type of economy to apply the Cashu protocol and technology within this proof of concept.

**Simple primer content** (more resources listed below) 
- [https://timebanking.org/howitworks/](https://timebanking.org/howitworks/)
- [Video: Time Banking animation](https://www.youtube.com/watch?v=aB8ifVJ34JU)
- [Numismatics wiki](https://en.wikipedia.org/wiki/Numismatics)

**Examples of Time Banks**
- [Custom GoogleMap with Pins for all Time Banking ommunities globally](https://www.google.com/maps/d/viewer?mid=1ZZRA7ombZ7CN_8u8gHIi0wRxq45FaFWs&ll=23.581971987838646%2C2.24820156946123&z=2)
- [Tempo Time Credits](https://wearetempo.org/)
- [Time Banking USA](https://timebanks.org/)
- [Time Banking UK](https://timebanking.org/overview/)


## Addressing the 'how do you value one hour' question

This is a fundamental question of any economic system but is especially of relevance to Time Banking systems, which have been discussed at length within books and discussions within alternative currency and economics fields. The crux of this discussion is generally framed as something along the lines of:

**how can 1 hour for a skilled Doctor with specialized tools be the same as 1 hour of a gardener cutting the grass?**

This question is outside the scope of this current proof of concept but something that should be addressed. I believe the decision on such questions is a social consensus problem concerning how the members of a social group collectively decide to operate within *their own sovereign Time Bank*. There have been a plethora of implementations of Time Banks with different 'variations' but all the ones I have seen do not allow for the exchange of 'time' within their systems with real world assets or fiat. Time itself is the value in without any additional attribution to it - **within Time Banking communities this 'time' can be considered social capital, kudos, karma, being a good lad, being considered trusted, valued, or import within that group.** 

It is not something that will be solved with a technological solution such as the etime system I am proposing, but rather by organizational methodologies to find a share social consensus and process of governance around their rule-set. It is not up to us developers to decide how a community could put into action a Time Bank, but rather to provide the tooling for when such systems are established by others. 


## An experiment in new forms of collectively ascribing 'value'

What I will add that this is a question on whether any economic system needs to have an abstact numismatic value attributed to a real world action that is the time a person invests/spends/uses in helping another person, creating a good or service useful in the local economy, volunteer in public goods within society, pay their fine/punishment for sanctioned behaviour within the community.

The action of ascribing value to an object in the real world is a social consensus problem, something that is of interest when considering a hyperbitcoinized society which no longer is ascribing a fiat 'value' to their satoshis. In this proof of concept I wish to offer tooling for a system which no longer ascribes any fiat 'value' to their time, time in itself is the unit of account and the 'value' is the application of that time to their community or economy.

For more on this thought experiment I recommend reading online (for free) [this book called Sacred Economics](https://sacred-economics.com/read-online/)


## Why not just use Bitcoin?

This proof of concept is applying the ecash model to minutes, hours, days - what can be called 'person-hours' to create a blind signature system to respesent their economic interactions as 'etime' 

This 'etime' is not meant to be backed by satoshis/Bitcoin within the mint, but a system could leverage both and have a satoshi 'value' for the 'etime' within an economic system (see below: Citadel public goods idea)

Time Banking systems do not require a digital collateral to back the etime, as what is at stake is a person's reputation and power within a closed community group that will punish bad actors and incentivise public goods. 

This context document is also an invitation to a thought-experiment: Can you design a economic system without attributing abstract value to your unit of account. In Bitcoin our unit of account are 'satoshis', to which we collectively ascribe and try to reach consensus on the price of a satoshi in fiat terms (USD/EUR/etc), but within the Bitcoin network they do not have any more value that what they are. 1 satoshi = 1 satoshi or 1 Bitcoin = 1 Bitcoin. 


## Design choices for project

- 100% offline use (no http/API)
- should run on smartphones made after 2010 (ideally a PWA)
- access-control to the mint (not open to anyone)
- etime notes represent minutes of real time (time counter mechanism)
- no 'withdrawl' or 'deposit' logic (no exchange of etime for other assets)
- ability to cryptographically query the mint for unique audits (more transparency with verifiability)


## Relevant features of Chaumian ecash for time banking

- Offline blind signature exchange
- Feeless blind signature exchange
- Creation of any denomination (melt/mint)
- Low-resource requirement
- self-hostable
- low/no-latency contexts
- asyncronhous mint interaction
- programmable auditability (not just Proof of Liabilities)
- cdk / MIT license
- written in Rust

## Use-case scenarios

From my brief research into current Time Banks there are 4 active communities that could test this project today, but the core use-case would be for emergent Time Banking systems - a few identified use-cases are the following:

#### remote / off-grid cashless communities

**number of members: 10 - 100**

By remote or off-grid I am implying limited or no internet connectivity, potential for power brown/black-outs, locations not serviced by local ISP or cell providers, or simply communities that can not afford the fiat price for services such as starlink or even a mobile data plans.

This community ideally all live within a 15 km area and they meet in person, share resources, assist each other in times of need and have a set of shared values including the wish to not have a fiat/numismatic economy between members / being in a 'transactional relationship'. These sorts of communities already exist all over the world, usually in smaller settlements, where their interal community economy already operates on a 'help your neighbor' approach. An example of this being where other members of a community help with the harvest of the wheat field of one member, so that other members can have access to flour and make bread for all the members of the community (bread being a public good). Another example would between two members of a community who help each other with discrete tasks or share tools to help their individual activites - what in past we called 'being a good neighbor' - without the expectation of something in return (gifting economy).

With respects to eTIMEbank this community would have to seek social consensus on what the 'mint' is, how it is hosted, who has access to the mint, what the unit 'etime' is denominated in (minutes, hours, days), and how to resolve disputes and issues - prior to establishing a mint and setting up wallets for users.

In terms of technology stack, all the members of this community would have a stock android smart phone from 2010 onwards, this could also allow to setup a mesh network or bluetooth gossip protocol between the devices (out of scope here). For the mint it could be a laptop, modded wifi router, or a rasperbby pi with wifi hotspotting capabilities and an antenna, which would be ideally placed in or near the location where members meet regularly (asynchronous melting/etime updates). This is up to the community, their resources, setup and implementation wishes.

**Benefits in this use-case:** 
- Feeless offline transactions of time between members
- Programmed auditability of the mint to produce reports for community
- Allows for incentiviation of public-goods within community


#### Volunteer-run events 

**number of members: 100 - 10k**

`TO DO`

#### Incentivising pro-social behaviour / public goods

**disbursement of a pre-funded community treasury**

`TO DO`

#### Bitcoin Citadels / Journeyman model

**Community PoW & incentivising journeyman services**

`TO DO`

Journeyman - Def

## Time Banking resources

- [https://timebanking.org/howitworks/](https://timebanking.org/howitworks/)
- [https://timebanks.org/start-a-timebank](https://timebanks.org/start-a-timebank)
- [Time Banking wiki](https://wikipedia.org/wiki/Time_banking)
- [Numismatics wiki](https://en.wikipedia.org/wiki/Numismatics)
- [Alternative currency wiki](https://en.wikipedia.org/wiki/Alternative_currency)

### Video

- [Video: Time Banking animation](https://www.youtube.com/watch?v=aB8ifVJ34JU)
- [TEDxDouglas: How timebanking can help rebuilding community spirit - Valerie Miller](https://www.youtube.com/watch?v=VRHvoYas82g)
- [TEDxStPeterPort: Timebanking in the UK: It's About Time - Sarah Bird](https://www.youtube.com/watch?v=k0Flh6cuuWs)

**Examples of Time Banks**
- [Custom GoogleMap with Pins for all Time Banking ommunities globally](https://www.google.com/maps/d/viewer?mid=1ZZRA7ombZ7CN_8u8gHIi0wRxq45FaFWs&ll=23.581971987838646%2C2.24820156946123&z=2)
- [Tempo Time Credits](https://wearetempo.org/)
- [Time Banking UK](https://timebanking.org/overview/)
- [bespoke time banking software by Time Banking UK](https://timebanking.org/software/)
- [Time Banking USA](https://timebanks.org/)

**Other Sources**
- [Huffpost](https://www.huffpost.com/entry/bringing-people-together_b_8916374)
- [Vice Portugese - O banco que quer seu tempo, não seu dinheiro](https://www.vice.com/pt/article/o-banco-que-quer-seu-tempo-nao-seu-dinheiro/)
- [Book: Give and Take: How timebanking is transforming healthcare](https://books.google.com/books?id=LIiSBQAAQBAJ)
- [Timebanking (CCIA – 2015)](https://monneta.org/en/timebanking-ccia-2015/)
- [Sacred Economics: money, gift and society in the age of transition - Charles Eisenstien](https://sacred-economics.com/read-online/)

**Academic papers**
- [Introduction to time banking and Time Credits, 2016](https://www.researchgate.net/publication/297696050_Introduction_to_time_banking_and_Time_Credits)
- [Participação em bancos de tempo: utilizando dados sobre transações para avaliar o Banco de Tempo - Florianópolis](https://www.apec.org.br/rce/index.php/rce/article/view/16)
- [Banco de Tempo-Florianópolis: análise das características socioeconômicas de seus membros](https://ojsrevista.furb.br/ojs/index.php/rbdr/article/view/6937)
- [Time banks: rewarding community self-help in the inner city?](https://academic.oup.com/cdj/article-abstract/39/1/62/268434)

