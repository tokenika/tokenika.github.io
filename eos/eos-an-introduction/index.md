# EOS - an introduction

**Current technologies for blockchain fall short of providing what developers and end-users need in order to contract together and to build large scale businesses. We propose EOS, a performance-based and self-governing blockchain that provides an operating system for building large-scale consumerfacing distributed applications. This paper outlines the context, vision and software architecture underlying EOS, which we are building to serve a broad and diverse group of users with smart business.**

> The following text is an abbreviated (and slightly edited) version of Ian Grigg's article.

### What is it that our user needs?

In the abstract, she wants to:

* Know her friends, business partners, and customers.
* Communicate with them.
* Be able to contract with them:
  * in the small, make peer to peer agreements,
  * in the large, build a sophisticated business to be able to serve the market.
* Be able to retain and direct her value (pay bills, etc) as a necessary component of business.
* All has to be done safely and securely.
* Be able to invest in a predictable business. This is a complex issue, but appears to require three components.
  * Know that the ecosystem is advancing, and not at undue risk of failing.
  * Pay for development effort up front with reasonable payback in the future.
  * Because she knows that things - contracts, assets, transactions, intents - go wrong, she wants to be able to fix her difficulties. Including, with her friends, her business, and her assets, and quickly, cheaply and without undue escalation.

### Current landscape

It has become abundantly clear that for one reason or another, the promise of universal peer to peer contracting and money has been excluded to the wider Internet:

* Bitcoin is too unsafe, and its smart contracts opaque.
* Ethereum is too scary, too hard, too geeky.
* Corda is ‘big corporate.’

##### Bitcoin

As the platform that launched the first and most successful cryptocurrency, Bitcoin is a baseline. Yet, as the ‘first’ its flaws shine as bright as its success: The UTXO verification model means that complex smart business has to be mediated through external code. The state is nicely locked on chain, but the hard work of negotiation is done by the applications.

Its lack of a thoughtful governance layer results that upgrades are very difficult, and the community is at war with itself.

##### Ethereum

To rectify Bitcoin’s weaknesses, Ethereum establishes a Turing-complete virtual machine capability on a
world-wide computer. It has several major shortfalls. Firstly, it has a dramatically restricting requirement to find consensus on state over thousands of program executions, leading to resource congestion at around 15 TPS. Secondly, the decision to go-it-alone on languages, VMs, toolkits and the like has caused a drag on developer capabilities. Thirdly, it suffers from the adhocracy of the Foundation that has emerged despite the refusal of major stakeholders to recognise the need for governance.

As an emergent business proposition, use of Ethereum has been dominated by raising funds for projects mostly aimed at finishing Ethereum as a platform, or competing with it. Few novel use cases have made their mark, suggesting that there is more work to do before the Ethereum concept of smart contracts bears fruit.

##### Corda

The primary distinguishing factor of Corda is that it is not a blockchain but a framework for party to party
workflow. Instead of posting contracts and actions to a blockchain, parties exchange messages and come to consensus via notaries. It achieves confidentiality for parties, high performance unconstrained by chain coordination, and the ability for parties to control the contracts as they succeed and fail.

Yet workflow works best with small numbers of parties, not large, and hence it is weaker on issuance of assets, especially cash and cash-denominated trading. Another weakness is that Corda’s walled garden approach stops it being an attractive mass market for small players.

### The vision

What is needed is smart business for the everyday person. An everyday distributed application needs to live in a global blockchain that is open to everyone, has enough performance to build big business, is
connected enough to bring people together and is safe and secure enough that businesses from different regions of the world can trade with each other.

Thus, the vision before us is a single global contracting blockchain that can scale up to handle a long-tail of businesses negotiating contracts for mutual advantage in a safe and secure environment.

### Principal features

EOS design predicts a blockchain to handle thousands of transactions per second for business contracts that are captured in easy to use and easy to secure languages. The major features include:

* High performance messaging using event sourcing
* Delegated Proof of Stake as the consensus mechanism
* Contracts as negotiation and intent, with messaging at its heart
* Usability for the user, contract writer, developer and entrepreneur
* Governance for business and chain maintenance

##### High performance messaging using event sourcing

The EOS design switches from the more popular *consensus over state* to the less familiar *consensus over events*. As a result, what we get is a blockchain made of *events* rather than *state*.

In building a practical state machine, we have a choice between saving events or saving state, which choice depends mostly on what we are trying to optimise.

* A machine saving state is more likely to be used in a context where we focus on what state it is in now, e.g. a database.
* A machine saving messages as intent is more likely to be useful when asking *how* we got to the state we are in now, e.g. a contract.

Restart is faster with saved state, throughput is faster with saved messages. Because users need performance, the EOS design opts to save messages rather than state.

##### DPOS as the consensus mechanism

For consensus over messages, the EOS architecture uses Delegated Proof of Stake (DPOS), a two-tier governance structure proven in Steem and Bitshares.

In the first tier, block producers are elected into a round of 21. In the second tier, each producer gets the right to produce one block per round, and is rewarded for the validation of incoming messages and production of the block of messages. A block released by one producer is validated by the next and the next and so forth; if not validated, it is not built upon. 

Similar longest-chain mechanics to Bitcoin are followed, and in short order, the producers converge on
a longest chain. A block that is accepted by a quorum of producers is declared immutable, and the chain of immutable blocks becomes in effect a checkpoint.

Like proof of work, producers can censor (ignore) messages, or they can front-run by introducing their own from their superior knowledge of the future. To provide light-touch governance over bad acts by producers, each round of producers is continuously elected by the community using proof of stake (PoS). 

In effect, a set of Generals is chosen for a campaign, and each get one turn. After the campaign, the civilian community asserts its view to replace any bad Generals.

DPOS avoids the tax of mining, releasing that substantial value back to stakeholders. Value from block rewards would be initially captured entirely by the producers. However, because they are elected by the community, they are incentivised to share the rewards by a scheme that producers agree on amongst
themselves, and promote to the community.

By constitution, the long term reward for producing blocks can be limited to for example 5% per annum.

##### Contracts as negotiation and intent, with messaging at its heart

Messages are the natural element of contracting, as they better capture all phases of successful contracting: negotiation, intent, performance and breach of obligations are all events better captured as messages than, say, state. From the perspective of a contract, the arrival, acceptance and processing of a message is a simpler abstraction than state.

An order book in a messaging-based system is committing to its set of incoming messages and outgoing set of messages, which is a relatively tractable task. In contrast, in a fully state based system, all traders have to negotiate the acceptable state to all of many parties, including quantities and prices, before submitting a final state to the blockchain.

##### Usability for the user, contract writer, developer and entrepreneur

The direct user of a blockchain is the developer who creates web apps for her end-users. To support an end-user, the software must support the developer. High impact support for the the developer includes (a) the tools, (b) the language, and (c) the environment.

In the large, the EOS developer will be supported by a web-based toolkit that provides a fully-serviced framework on which to build applications as distributed web-based systems coordinating over the blockchain. Accounts, naming, permissioning, recovery, database storage, scheduling, authentication
and inter-app asynchronous communication are all built in. A goal of the architecture is to provide a fully-provisioned operating system for the builder of apps, focussed to the web because that’s where the bulk of the users are.

The direct users of a blockchain such as EOS are the entrepreneurs and developers who write contracts to implement distributed applications (DApps). Their users are the routine customers in retail, finance, logistics, media. Those latter customers do not need to know what a blockchain is. Hence the goal is to give the developers a platform that allows extensive business logic to be built, but the mechanisms of
communication are hidden.

The DApp developer is given a fully capable accounts, permissioning and messaging platform in which to express the system. The user interface matches what users are familiar with - a webkit for building websites and of course access to the blockchain. This approach is expressed as “an operating system for blockchain.”

##### Governance for business and chain maintenance

It is a reality that things go wrong with automated processing of contracts, to the distress of all. It is our hope to reduce both the frequency and the cost of those errors, but they cannot be eliminated entirely, and our approach is to build in remedial methods for when they do occur.

A blockchain based on EOS software assumes that all who use the blockchain are members under a short Constitution and by agreeing to which, all members form a Community subject to the Constitution.

The Constitution sets down some basic rules for the benefit of the community. The Constitution empowers three arms of governance:

* arbitration for resolving disputes,
* block producers for choosing blocks,
* and referenda for community voice.

Arranged in an interlocking triangle of governance, these three arms support and counterbalance each other:

* Referenda are used by the community to vote in the producers and arbitrators, as well as changes to code and constitution.
* Arbitrators can deliver legally binding rulings to resolve disputes, and also for extraordinary changes such as hard forks.
* Block producers are at technical liberty to censor bad transactions or introduce remedial ones - but are mindful of community reaction. 

In other words, block producers have the freedom to decide about enforcing rulings published by the arbitrators, but if their decision is wrong they risk being voted out by the community.

This counterbalanced arrangement ensures that no party or group has total power. Even founders or developers have only limited ability to affect the rights of the community members. Hard forks and other upgrades have a defined path, and individual disputes are channelled to a place where we can resolve and get back to business.

To make these institutions work, users have to agree to the Constitution, which empowers the producers to choose blocks, and reserves all disputes into the forum of arbitration. As well, the Constitution creates the legal rights expressed in the blockchain by stating that each member receives those rights properly accounted for, and in return each member supports the accounted rights of others. This trade of your rights for the rights of others becomes the cornerstone of the community, in that the community is defined by both the usage of the platform and the agreement to the Constitution.

### Use cases

An EOS blockchain is intended for highperformance messaging with business logic. Popular use cases will include supply chain, resource management, user messaging such as social media, asset issuance and trading, accounting for remittances, and gaming.

A typical use case might be Uber. Ride-sharing is based on setting standards of behaviour for the driver and for the passenger. If drivers and passengers were part of the same community, there would be an immediate benefit - the base of liability and standards of behaviour would be covered under community constitution and dispute resolution, and their contracts could be bilateral rather than intermediated, thus
minimising any regulatory difficulties.

Then, as the contracts can be bilateral, the business flow could be split up: tracking passengers in the market, tracking cars available, finding a match, negotiating a contract, performance, settlement, pricing, and social tracking could all be built as separate DApps that interact.

### Community

To support business, we need to solve problems. And to scale the solving of problems, it has to be done by the community itself, which means it has to be embeded in the architecture. To advance community, we must preserve open entry, but on entry provide the tools that users find useful for governance. 

When bound together as a community under a Constitution, users will know that the rights, liabilities and obligations of their counterparties are at least to a basic standard, as expressed in a constitution and as enforced in dispute resolution. In addition reliable names and a web of trust can reduce the anonymity of the Internet and give people a sense of belonging to something important.

<span style="color:silver;font-size:11px">Source: [iang.org](http://iang.org/papers/EOS_An_Introduction.pdf) by Ian Grigg, July 2017</span>
