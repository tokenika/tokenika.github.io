# EOS - the next step after Ethereum?

1. Our background. (2 minutes) (TM/DW)
2. Quick survey "State of the blockchain today". (5 minutes) (TM/DW)
3. Major problems facing the crypto-space as of 2017. (5 minutes) (JZ)
   * Scalability
   * High/unpredictable transaction fees
   * Private key security
   * Blockchain governance
   * Smart-contracts running amok
   * Confidentiality of transactions
4. EOS presentation. (20 minutes) (JZ)
   - What is EOS?
   - What features make EOS unique when compared to Ethereum?
   - What are EOS weak points?
   - What are EOS strong points?
   - EOS roadmap
5. About Tokenika. (4 minutes) (TM/DW)
   * What we do?
   * What we need?
6. QAs (4 minutes)

Total: 40 minutes.



---

## Disclaimer

This presentation will be about a smart-contract system called EOS but we are in no formal way associated with the company developing EOS code. They are not paying us and this definitely is not meant to be a sales pitch for EOS. Actually we have no direct interest in you buying EOS tokens and this certainly should not be treated as a financial advice. We are just part of EOS community and our aim is to encourage you to take interest in the concept and possibly consider building businesses on top of EOS.

## ad 1. Our background

* Our background is very wide - spanning from the manufacturing industry, real-estate, education and public agencies. We're strongly based in reality:
  * We run real businesses employing several hundreds of people. 
  * One of us runs a real-estate association with over 8k members.
  * One of us, Krzysztof Piech, is a publicly known figure promoting the crypto industry in the mainstream media and state agenesis.
  * We have active business connections with China.
* We are blockchain veterans. We started with BTC and went through the mining phase. Then we repeated the same success with ETH and other major projects. In most cases we invest and hold.
* We actively participate in the blockchain space. This year alone we've been to the FinTech Week in London and Blockchain Summit in Shanghai. We've talked to the people behind some the major projects, including Ethereum, Iota, Factom, Gnosis.



## ad 2. Quick survey "State of the blockchain today"

- What is the total of BTC mining revenue per day? (12 mln USD / day)
- How much are we spending on BTC and ETH mining per year? (5 bln USD, which is much more then the total of all ICOs)
- What is BTC average transaction fee? What about ETH? (3 USD & 0.30 USD)
- How many transactions per second is BTC able process? What about ETH? (4 trxn/sec & 30 trxn/sec)
- Which are the four top blockchains currently in production which handle the biggest number of transactions? (BTC, ETH, Steem, BitShares)
- How many transactions per second does Facebook require? What about Visa? (50k trxn/sec, 2k trxn/sec)
- What is the current record of transaction processing in the crypto-space? (3k trxn/sec by BitShares)





## ad 3. Major problems facing the crypto-space as of 2017

- #### Scalability

  Scalability is considered to be the number one problem facing all major blockchains, especially Bitcoin and Ethereum. The only way to tackle this issue boils down to relying on a second layer of transaction processing: Lightening Network for Bitcoin and Raiden for Ethereum. Is it any good? Well, kind of.  Those solutions are based on so called state channels: you make a series of off-chain transactions and when you're done you settle them on-chain. So it's best suited for recurrent payments between the same parties. And it doesn't handle smart-contracts.

  Ethereum has also got a scaling solution called Plasma, which is basically a tree of chains. There are two major problems with it: it's still just at a proof-of-concept stage and it's inherently less secure.

- #### High/unpredictable transaction fees

  It has become evident that none of the many businesses currently being built on Bitcoin or Ethereum can have any economic viability at the current level of transaction fees. As fees are entirely under block producers’ control, the only way to address this problem is to rely on the second layer transaction processing, which I've just described, and assume that transaction fees applied there will be significantly lower.

- #### Private key security

  How to handle the inevitable problem of people losing access to their blockchain accounts? It can happen for various reasons: they get hacked, they forget their passwords, they lose their mobile phones or computers. Apparently there is no solution currently available. The experts say this is the "inherent" feature of a blockchain. Is it really the case? Bear with me and we'll find out quite soon.

- #### Blockchain governance

  This problem has been raised for a long time by the smartest people in the space. How to make decisions in a decentralized environment? And I mean decisions in business-as-usual situations (e.g. budgeting) as well as decisions needed in emergency situations (when something goes seriously wrong, e.g. the DAO).

  You need to have an efficient voting system in place. Bitcoin has none. Project like Ethereum or Dash have some kind of voting in place. But imagine what happens when there is a moral dilemma? When different groups of community expect different outcomes - is a fork the only way out? Or when there is an emergency and there is no time for voting - you need to act immediately?

- #### Smart-contracts running amok

  One possible solution preventing smart-contracts getting out of control is to find a way to formally verify their code before they are deployed. The problem is that it's very hard in practice. Formal verification makes things difficult. And as of now, it just reduces the risk but does not give 100% guarantee the code will run as expected. So you can make a lot of effort, but still you need to be able to handle a black swan. Or you're out business.

  Look at the schizophrenia Ethereum needs to go through in order to justify its existence. They clearly try to eat the cake and still have the cake. Their website still says: *Build **unstoppable** applications*. Right, unstoppable, this is what it says. Are they really unstoppable? We all remember *The DAO*, don't we?

  Please don't get me wrong. I'm not making a judgement about the way people behind Ethereum sorted out the mess. I'm making a judgement about them being unprepared to handle the situation in an orderly manner. And guess what? No lesson seems to be learned - they are as unprepared for a black swan now as they were back then. Clearly handling a smart-contract running amok is not considered to be part of their business.

- #### Confidentiality of transactions

  This is a tough one. How to reconcile our desire for confidentiality with our desire for transparency? When business A does a deal with business B, does it have to be visible to the rest of the world including their competition? In traditional business we are used to the notion of trade secrets, so if we want to build blockchain-based solutions for real-life businesses, we need to somehow address this requirement.



## ad 4. EOS presentation

* #### What is EOS? 

  * An operating system for building decentralized applications. Its *raison d'être* is similar to Ethereum's yet EOS tackles a much wider problem.
  * Evolution: payment system >> smart-contract system >> operating system for decentralized applications. Those words are being used on purpose: it's not just a system, it's an **operating system**. And it doesn't just run smart-contracts, it runs **decentralized applications**.

* #### What features make EOS unique when compared to Ethereum?

  * Processing power

    While other systems definitely require a second layer of processing to be able to scale, EOS offers enormous processing power in its primary layer. This is the result of the following features:

    - EOS consensus mechanism (DPOS, Delegated Proof of Stake) introduces a fixed number of block producers. As a result, time intervals between blocks are exactly 3 seconds, and with an improved server infrastructure can be reduced even more. It’s worth noting that despite this limited number of block producers, DPOS is the most decentralized system in existence - provided we apply [a rational measure of decentralization](http://bytemaster.github.io/article/2015/01/13/Decentralization-of-Nxt-vs-BitShares/).
    - EOS blockchain maintains *consensus over events* instead the common approach of *consensus over state*. As a result, it takes longer to restart a network node but on the other hand transaction processing is much quicker. This is a very beneficial trade-off, as node restarting is a rare event, while efficient transaction processing is what's needed most of the time.
    - Currently all blockchains rely upon sequential processing of transactions; this fundamentally limits the throughput of a blockchain to the computational capacity of a single CPU core. EOS architecture has been designed as [multi-threaded on the very fundamental level](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#deterministic-parallel-execution-of-applications). Not everything can be executed in this way (e.g. managing an order book of a decentralized exchange), but those things which can (e.g. validating a smart-contract's preconditions) are subject of parallel processing. EOS is extremely fast in sequential processing and gets an extra boost when the parallel processing mode kicks in.
    - EOS enables [partial evaluation of blockchain state](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#partial-evaluation-of-blockchain-state). This means that an EOS node can selectively process transactions and ignore those which are of no interest for it. The assumption is that everyone should not have to run everything, especially if they only need to use a small subset of the applications.

  * Addressing a much wider context

    In EOS smart-contracts are treated as a very broad phenomena. The assumption is that human errors in smart-contracts are unavoidable, so there needs to be a built-in mechanism which handle such cases. EOS will have:

    * a constitution encoded in the blockchain,
    * arbitration for resolving disputes
    * and stakeholders voting on important decisions.

    Had *The DAO* incident happened on EOS, there would be a clear procedure to follow to resolve the issue in an orderly manner. It’s clear that EOS is designed with the needs of serious businesses in mind: before they commit their resources and their precious reputation to a large blockchain project, they need to be sure there is an emergency procedure in case things get out of control.

  * Complete operating system

    We have all those exciting ideas in the crypto-space but actually nothing is coming to market. All we have are just prototypes. The developers are trying to build these amazing applications but they don't get to spend their time on building business logic. Instead they are stuck on things like databases, storage and inter-app communication.

    What we are missing is an operating system.

    EOS is much more than just a decentralized computer. Actually, it is a full-blown decentralized operating system, including a built-in storage solution based on IPFS. What this means is that there are features embedded right in the blockchain which can be utilized by any advanced application built on EOS. Those include: databases, account permissions, account recovery, scheduling, authentication, inter-app communication. Thus application developers building on EOS only need to write code for what is unique for their application, whereas the fundamental functionality is delivered by the blockchain itself.

  * Web Assembly as a compiler

    Smart-contracts in EOS will be compiled to [WebAssembly](http://webassembly.org/), which is an emerging industry standard backed by Microsoft, Google, and Apple. The goal of this standard is to make it possible to run untrusted high-performance code in your browser. [WebAssembly is a big deal](https://medium.com/mozilla-tech/why-webassembly-is-a-game-changer-for-the-web-and-a-source-of-pride-for-mozilla-and-firefox-dda80e4c43cb), as it will enable high performance web applications such as video and image editing and games. It provides a universal compile target that enables applications to be developed in any language, ranging from C++, Java & C# and JavaScript. There is even work going on to compile Solidity to WebAssembly.

  * No transaction fees

    From the business point of view, it is hard to defend the paradigm of end-user being forced to pay for the mere fact of interacting with an application. Unfortunately, this is the standard case in the current crypto-space: it's rental-based (pay-as-you-go), instead of owner-based. A Steem-like application could not have survived in such a model. EOS offers a solution which prevails in business around the world: you can own a piece of infrastructure and its resources and then use them freely, not just rent them - this is obsolete. In EOS the deal is simple: if you own 1% of the tokens you own 1% of the network, including all it's resources: the bandwidth, the storage etc.

  * DPOS - the most decentralized & resilient consensus system out there

* #### What are EOS weak points?

  * Low awareness and quite a lot of negative (undeserved?) perception, mainly due to people being skeptical about the viability of the claims contained in EOS whitepaper.
  * Almost non-existent ecosystem and very few developers outside of the core team, capable to contribute to the code.
  * Not live yet. I'll tell you about the roadmap in a sec.

* #### What are EOS strong points?
  * Small yet very efficient & experienced team

    Dan Larimer's track record: very fast & very powerful. It's the same team that has built BitShares and Steem, which is the most complex blockchain in existence today: conceived, designed, built, launched in just 6 months.

    As of now, the team has 26 developers, which is a fraction of what Ethereum has at its disposal, yet probably the biggest team in history under Larimer's management as CTO.

  * Rare combination of the top talents in the crypto-space, entrepreneurial skills, and strong financial backing

    We have Dan Larimer and Ian Grigg as the main source of brain power. We have Brendan Blumer as CEO, a young yet very experienced and successful entrepreneur. And we have powerful investors like Brook Pierce and Bo Shen from Fenbushi Capital (the same which was an early investor in ETH) financially backing it, with Pierce even personally engaged in promoting EOS.

    So even if it ends badly, we are in a good company.

  * Concept proved in practice

    All existing smart-contract platforms are being built without any prior experience with building decentralized applications. How can I build a platform for decentralized applications if I've never built a decentralized application? Steem and BitShares - they are very different. One is a decentralized exchange and the other is social media. What they were able to do is look at them and figure out what's common between them. EOS is the result of this.

  * Commitment to spend 1 bln USD to boost the ecosystem

    Brendan Blumer: *EOS is the most well funded project in history and we plan to soon announce a program for up to one billion USD of capital for EOS projects. We’re amidst onboarding a few critical partners first that will give EOS and this program the world-class credibility it deserves.*

* #### EOS roadmap

  * The project was started in Q1 2017, it was publicly announced in May 2017.
  * Right now we have a MVP stage called *EOS Dawn*. You can run a standalone EOS node and play with smart-contracts using command line tools.
  * By the end of the year an EOS version featuring all major functionalities will be released.
  * Q1 & Q2 2018 devoted to testing and building development tools & documentation. During this phase you can starting building apps running on the testnet.
  * The blockchain goes live in June 2018.



## ad 5. About Tokenika

* #### What we do?

  * Our focus is on blockchain-based fundraising and digital asset management. Projects like NeuFund, Melonport are Iconomy are the best approximation of the domain we want to be in.

    We believe that just as there has been an ICO frenzy on Ethereum for the last couple of months,  there will be a similar one on EOS. This time by businesses who actually want to build production-ready apps, not prototypes or proofs of concept. Real apps used by real people, i.e. not only blockchain folks.

    So we want to be prepared for this happening: businesses wanting to raise funds and investors wanting to risk funds, and then manage their cryptocurrency portfolio in a convenient & secure manner.

  * We are setting up a software house dedicated to building dApps (both on EOS and ETH). We are already experimenting with EOS smart-contracts and already have third-parties manifesting interest in using us to convert their ideas into EOS apps.

  * As far as EOS is concerned, we aim to become one of the 20 block producers (called *witnesses*) once the system goes live.

    How realistic is that? Well, it depends how determined you are. Unless you are a major stakeholder of EOS (which we are not), the only way to do it is via building a strong reputation in EOS community. How do you do that? By doing things which are considered to be beneficial for EOS and its ecosystem by its community and EOS shareholders. It's similar to an attempt to be elected to the board of directors in a publicly traded company.

    As you can see we've been doing various things to this end and actually this very presentation is part of the process.

    And obviously to be a viable witness candidate you need to be able to handle the server infrastructure and make it both robust and secure. I guess we can manage that as our main advisor, who prefers to remain anonymous, is already a witness for Steem.

* #### What we need?

  * Contrary to most folks out there, we're not looking for money. We are looking for ways to spend money.
  * Looking for good ideas that can be converted into dApps.
  * Hiring developers with background in C++ and/or ETH smart-contracts.