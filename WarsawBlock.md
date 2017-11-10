# EOS - the next step after Ethereum?

1. Our background. (2 minutes) (TM/DW)
2. Quick survey "State of the blockchain today". (5 minutes) (TM/DW)
3. What do decentralized applications require? (2 minutes) (JZ)
4. Major problems facing the crypto-space. (5 minutes) (JZ)
   * Scalability
   * High & unpredictable transaction fees
   * Private key security
   * Blockchain governance
   * Smart-contracts running amok
   * High cost of app development
   * Bad user experience
   * No bridges between blockchains
5. Introduction to EOS. (18 minutes) (JZ)
   * What is EOS?
   * What features make EOS unique when compared to Ethereum?
   * What are EOS weak points?
   * What are EOS strong points?
   * EOS roadmap
   * Wrap up
6. About Tokenika. (4 minutes) (TM/DW)
   * What we do?
   * What we need?
7. QAs (4 minutes)

Total: 40 minutes.



---



## Disclaimer

* This presentation will be about a smart-contract system called EOS. However we are in no formal way associated with *block.one*, the company developing EOS code. We are just part of the emerging EOS community.
* We have no interest in you buying EOS tokens, and this certainly should not be treated as financial advice. Our goal is to encourage you to take interest in the concept and possibly consider building businesses on top of EOS.



## ad 1. Our background

* Our background is very wide - spanning from the manufacturing industry, real-estate, education and public agencies. We're strongly based in reality:
  * We run real businesses employing over 800 people. 
  * One of us runs a real-estate association with over 8k members.
  * One of us, Krzysztof Piech, is a publicly known figure promoting the crypto industry in the mainstream media and state agenesis.
  * We have active business connections with China.
* We are blockchain veterans. We started with BTC and went through the mining phase. Then we repeated the same success with ETH (we participated in Ethereum ICO in 2014) and other major projects. In most cases we invest and hold.
* We actively participate in the blockchain space. This year alone we've been to the FinTech Week in London and Blockchain Summit in Shanghai. We've talked to the people behind some the major projects, including Ethereum, Iota, Factom, Gnosis.





## ad 2. Quick survey "State of the blockchain today"

- How much in total are we spending on BTC and ETH mining per year? (5 bln USD / year, 12 mln USD / day, which is much more than the total raised by all ICOs so far: 3 bln USD)
- What is BTC average transaction fee? What about ETH? (3 USD & 0.30 USD)
- How many transactions per second does Facebook require? (50k trxn/sec)
- How many transactions per second is BTC able to process? What about ETH? (4 trxn/sec & 30 trxn/sec)
- Which are the four top blockchains currently in production which handle the biggest number of transactions? (BTC, ETH, Steem, BitShares)




## ad 3. What do decentralized applications require? 

- They need to be scalable and cheap to run. If you can't support millions of users, you can't build a business that's able to recover your initial investment. You can't compete on the market if your cost per transaction is substantially higher than your centralized competitors. So you're going to need thousands of transactions per second and you need them to be very cheap.
- They need to be free for your users. You don't want to charge micro payments every time someone loads your webpage or wants to sign up. You need to have access to freemium models or different monetization strategies. If you want to charge your users, it should be the application choice, not the platform it's running on. 
- They need to be available via mobile phones and web interfaces, so that users don't have to download and install anything. And they need to be responsive.
- Your users need account names, no public keys, no fancy cryptographic stuff. And they need a procedure for account recovery. Can you imagine **not** having account recovery, if you aim for mass adoption? And users need 2nd factor authentication, ideally biometric one on their mobile phone, instead of an additional device like Trezor.
- Your app needs to be upgradeable. No business plan survives first contact with the market. You need to be able to upgrade your app to keep your business afloat, to adapt to changing market conditions, add new features that users expect. If you can't do that then your application will stagnate.
- Your app needs bug recovery, something that's often overlooked in this space. Software is an imperfect art. You're guaranteed that statistically there will be a bug sometime. It doesn't matter how many eyes you have on it, doesn't matter how much formal verification you do, it doesn't matter what programming language you use - there will be bugs somewhere. So bug recovery and upgradability go hand in hand and you need to be prepared for it, if you want to have a realistic view of business and software development.




## ad 4. Major problems facing the crypto-space

- #### Scalability

  What is high-performance? These are the requirements of real industry. You have 20k transactions per second just to do a Visa and MasterCard, not to mention all the other payment systems out there. Facebook does 50k likes per second, not including all the posts and voting and other actions that the users take. If you're in the financial industry and you're trying to do trading it's sometimes a hundred thousand transactions per second per market pair. So imagine putting all of these on a single platform so they can interoperate. Well, that would require millions of transactions per second.

  This is what industry actually requires and this is what blockchain technology gives us today. There's a huge gap between what we can do and what we need to be able to do.

  If we look at Bitcoin or Ethereum, the only way to tackle this issue boils down to relying on a second layer of transaction processing: Lightening Network for Bitcoin and Raiden for Ethereum. Is it any good? Well, kind of.  Those solutions are based on so called state channels: you make a series of off-chain transactions and when you're done you settle them on-chain. So it's best suited for recurrent payments between the same parties. And it doesn't handle smart-contracts.

  Ethereum also has a scaling solution called Plasma, which is basically a hierarchy of blockchains. It's like a parent-child relationship: the parent blockchain acts a source of truth for the child blockchain. There are two major problems with this approach: it's still just at a proof-of-concept stage and it's inherently less secure.

- #### High & unpredictable transaction fees

  It has become evident that none of the many businesses currently being built on Bitcoin or Ethereum can have any economic viability at the current level of transaction fees. As fees are entirely under block producers’ control, the only way to address this problem is to rely on the second layer transaction processing, which I've just described, and assume that transaction fees applied there will be significantly lower. But still you have no way to predict the level of fees in the long run. And in some cases, you just need to have no fees at all. 

- #### Private key security

  How to handle the inevitable problem of people losing access to their blockchain accounts? It can happen for various reasons: they get hacked, they forget their passwords, they lose their mobile phones or computers. 

  If blockchain is going to go mainstream, there will be more and more unsophisticated users who can't be expected to secure their computer and perfectly protect their private key. We have to make it resilient so that eventually when their keys are compromised they can get their account back.

  This is extremely important. Because it's not just losing money - users who get hacked are also losing their identity, their reputation, all their followers. They need their account back and their name back or they won't use the platform again.

  Apparently there is no solution currently available. Apparently this is the "inherent" feature of a blockchain. Is it really the case? Bear with me and we'll find out quite soon.

- #### Blockchain governance

  This problem has been raised for a long time by the smartest people in the space. How to make decisions in a decentralized environment? And I mean both decisions in business-as-usual situations (e.g. budgeting) as well as decisions in emergency situations, when something goes seriously wrong and time is crucial.

  So you need to have an efficient voting system in place. Bitcoin has none. Projects like Ethereum or Dash have some kind of voting in place. But imagine what happens when there is a conflict between two different value systems? When different groups of community expect different outcomes - is a fork the only way out? Or when there is an emergency and there is no time to arrange a proper vote?

- #### Smart-contracts running amok

  One possible solution preventing smart-contracts getting out of control is to find a way to formally verify their code before they are deployed. The problem is that it's very hard in practice. Formal verification makes things difficult. And as of now, it just reduces the risk but does not fully guarantee the code will run as expected. So you can make a lot of effort, but still you need to be able to handle a black swan event. Or you're out business.

  Let's take a look at Ethereum. Their website still says: *Build **unstoppable** applications*. Right, unstoppable, this is what it says. Are they really unstoppable? Clearly handling a smart-contract running amok is not considered to be part of their business.

- #### High cost of app development

  Where are we today today? We have the decentralized computer and a bunch of people trying to build applications on top of it, some of them are quite exciting ideas. But actually nothing is coming to market. All we have are just prototypes. The developers are trying to build those amazing apps but they don't get to spend their time on building business logic and user interfaces. Instead they are stuck on figuring out low-level stuff like databases, storage and inter-app communication. 

  Furthermore, because everything's being implemented in the app layer, it's being done within relatively inefficient scripting environment. And even if it gets built, it will be expensive to use - it will cost gas.

- #### Bad user experience

  We must admit that user experience in the crypto-space is quite horrible. Can anyone name a blockchain-based application which can be used by normal people? Not by insiders like you, but by normal people, who just want to be users, not investors or risk-takers. An app which does not require you to buy tokens before you can try using it? An app which allows you do things in real-time, just as any conventional app like eBay or Uber?

  There is a reason for that. As developers are still stuck on making the back-end functional, there are no resources left to build the front-end. And even if they had the resources, you can't build a proper front-end if the back-end is unable to overcome the latency of block production. 

  The point is, if we want mass adoption, from the end-user perspective blockchain-based apps need to be indistinguishable from conventional apps. And unfortunately, despite all the hype, the technology right now is still too immature for that. We don't just need an efficient blockchain. We need the entire infrastructure around blockchain which makes it possible for front-end developers to do their job.

- #### No bridges between blockchains

  You're still unable to move value across blockchains without going through a centralized middleman. The precondition for that is asynchronous communication between decentralized apps. There are projects aiming to change that (e.g. Polkadot) but they are still years away from becoming a reality.




## ad 5. Introduction to EOS

* #### What is EOS? 

  * The simplest way to put it would be to say that EOS is a general-purpose smart-contract platform, just like Ethereum. But actually it's much more than that. EOS is a holistic approach to high-performance general-purpose consensus.

    Larimer: *EOS is the blockchain for building commercial scale decentralized applications that are indistinguishable from centralized alternatives.*

  * Evolution: payment system >> smart-contract system >> operating system for decentralized applications. EOS is an operating system for building decentralized applications. Those words are being used on purpose: it's not just a system, it's an **operating system**. And it doesn't just run smart-contracts, it runs **decentralized applications**.


* #### What features make EOS unique when compared to Ethereum?

  * <u>Processing power</u>

    While other systems definitely require a second layer of processing to be able to scale, EOS offers enormous processing power in its primary layer. This is the result of the following features:

    - EOS consensus mechanism (DPOS, Delegated Proof of Stake) introduces a fixed number of block producers. Time intervals between blocks are exactly 3 seconds and to become a block producer you just need to have a server hardware efficient enough to keep up with the demand. If you don't, you start missing blocks and you're voted out.

      By the way, quite recently EOS has announced that will be aiming at 500 ms blocks, instead of the current 3 seconds.

      But this does not mean you need a datacenter to be able to trust no-one and run a full node. EOS enables partial evaluation of blockchain state. This means that an EOS node can selectively process transactions and ignore those which are of no interest for it.

    - EOS blockchain maintains *consensus over events* instead the common approach of *consensus over state*. As a result, it takes longer to restart a network node but on the other hand transaction processing is much quicker. This is a very beneficial trade-off, as node restarting is a rare event, while efficient transaction processing is what's needed most of the time.

    - Currently all blockchains rely upon sequential processing of transactions; this fundamentally limits the throughput of a blockchain to the computational capacity of a single CPU core. EOS architecture has been designed as multi-threaded on the very fundamental level. Not everything can be executed in this way (e.g. managing an order book of a decentralized exchange), but those things which can (e.g. validating a smart-contract's preconditions) are subject of parallel processing. EOS is extremely fast in sequential processing and gets an extra boost when the parallel processing mode kicks in.

    - There is no concept of gas in EOS, so the virtual machine does not have to be bothered with the metering of every operation used by the code. 

  * <u>Much wider context</u>

    In EOS smart-contracts are treated as a very broad phenomena. The assumption is that human errors in smart-contracts are unavoidable, so there needs to be a built-in mechanism which handles such cases. EOS will have:

    * a constitution encoded in the blockchain,
    * arbitration for resolving disputes,
    * and stakeholders voting on important decisions.

    Had *The DAO* incident happened on EOS, there would be a clear procedure to follow to resolve the issue in an orderly manner. It’s clear that EOS is designed with the needs of serious businesses in mind: before they commit their resources and their precious reputation to a large blockchain project, they need to be sure there is an emergency procedure in case things get out of control.

  * <u>Blockchain governance</u>

    DPOS, EOS consensus mechanism, is designed just for that. Decisions can be made quickly, yet the ultimate power rests with the shareholders. Block producers have a strong motivation to make the right decisions and properly signal their intentions before taking decisions, or they get voted out.

    Strategic choices (e.g. the level of inflation and how to allocate this inflation) are decided directly by the shareholders.

  * <u>Complete operating system</u>

    EOS introduces the first blockchain operating system. What this means is that there are features and services embedded right in the blockchain and every application built on EOS has access to them. Those include: account permissions, account recovery, scheduling, authentication, inter-app communication, biometric 2nd factor validation.

    What's more, EOS provides every application with its own private database. The system has built-in storage solution based on IPFS, which is free to use, provided you're a token holder.

    Thus application developers building on EOS only need to write code for what's unique for their application, whereas the fundamental functionality is delivered by the blockchain itself.

  * <u>No transaction fees</u>

    EOS token is never consumed, which basically means there are no transaction fees and there is no concept of gas.

    EOS offers a solution which prevails in business around the world: you can own a piece of infrastructure and then use it freely, not just rent it on pay-as-you-go basis. In EOS the deal is very simple: if you own 1% of the tokens you own 1% of the network, including all it's resources: the bandwidth, the storage etc.

    If you have more resources than you need you can rent them out. If you run a business and don't have enough resources you can rent them from someone or buy more EOS tokens. The point is it's up to you, you have a choice.

  * <u>Asynchronous communication</u>

    EOS applications are designed with asynchronous communication from the start. What it means is that applications are designed to support communicating with other blockchains, as this kind of communication definitely has to be asynchronous. So we have internal communication with local applications as well as external communication with other blockchains, provided they support a compatible protocol. This allows you to have private enterprise chains that can communicate with a public chain.

* #### What are EOS weak points?

  * Low awareness and quite a lot of negative (undeserved?) perception, mainly due to people being skeptical about the viability of the claims contained in EOS whitepaper.
  * Almost non-existent ecosystem and very few developers outside of the core team, capable to contribute to the code-base. However this changes rapidly - there are already over 10k registered users on the Telegram EOS channel and 1k on EOS Dev channel.
  * The first language to be supported for EOS smart-contract creation is going to be C++. It's because this happens to be the first language supported by WebAssembly, EOS virtual machine. C++ is powerful but has a very steep learning curve. A less demanding language, like Java or C#, would be much more suited here but unfortunately those are not supported by WebAssembly yet.
  * Not live yet. I'll tell you about the roadmap in a sec.

* #### What are EOS strong points?
  * Small yet very efficient & experienced team

    Dan Larimer's track record: very fast & very powerful. It's the same team that has built BitShares and Steem, which is the most complex blockchain in existence today: conceived, designed, built, launched in just 6 months.

    As of now, the team has 26 developers, which is a fraction of what Ethereum has at its disposal, yet probably the biggest team in history under Larimer's management as CTO.

  * Rare combination of the top talents in the crypto-space, entrepreneurial skills, and strong financial backing

    We have Dan Larimer and Ian Grigg as the main source of brain power. We have Brendan Blumer as CEO, relatively young yet very experienced and already successful entrepreneur. And we have powerful investors like Brook Pierce and Bo Shen from Fenbushi Capital financially backing it. What's interesting, both were early investors of Ethereum (and still are), and Brook Pierce is personally engaged in promoting EOS.

  * Web Assembly as a virtual machine

    Smart-contracts in EOS will be compiled to WebAssembly which is an emerging industry standard backed by Microsoft, Google, and Apple. The goal of this standard is to make it possible to run untrusted high-performance code in your browser. WebAssembly is a big deal, as it will enable high performance web applications such as video and image editing and games. It provides a universal compile target that enables applications to be developed in any language, ranging from C++, Java & C# and JavaScript. There is even work going on to compile Solidity to WebAssembly.

  * DPOS - the most decentralized & resilient consensus system out there

    It’s worth noting that despite the limited number of block producers, DPOS is the most decentralized system in existence - provided we apply a rational measure of decentralization.

    The DPOS algorithm is divided into two parts: 

    * electing a group of block producers
    * and block production scheduling.

    Block producers are elected by stakeholders voting according to their stake. Hence the name: Delegated POS. The election part is what causes the most controversy, as it injects the human element back into blockchain, while we assume the reason we created a blockchain in the first place was to get rid of the human element. Well, this assumption is wrong. We created the blockchain in order to align human motivations properly, not to get of them. It's an illusion, as mathematically it's not possible to create a self-contained system which is completely independent from the outside world.

    As for the second part, block production scheduling, the main rule here is that it's invalid for a block producer to produce a block at any other time slot than the one they are scheduled for. This is a very simple rule, but its consequences are quite significant, for example:

    * Someone with even 50% of the active voting power is unable to select even a single producer on their own.
    * The system is robust under every conceivable natural network disruption and even secure in the face of corruption of a large minority of producers. 
    * Unlike some competing algorithms, DPOS can continue to function when a majority of producers fail. During this process the community can vote to replace the failed producers until it can resume 100% participation. I know of no other consensus algorithm that is robust under such a high and varied failure conditions.

    This gives DPOS the power to confirm transactions with 99.9% certainty in an average of just 1.5 seconds while degrading in a graceful, detectable manner that is trivial to recover from.

  * Concept proved in practice

    All existing smart-contract platforms are being built without any prior experience with building decentralized applications. How can you build a platform for decentralized applications if you've never built a decentralized application? People behind EOS have built BitShares and Steem - two systems originating from the same codebase, yet very different in functionality. One is a decentralized exchange and the other is social media. What the EOS team was able to do is look at them and figure out what's common between them. EOS is the result of this.

  * Commitment to spend 1 bln USD to boost the ecosystem

    Brendan Blumer: *EOS is the most well funded project in history and we plan to soon announce a program for up to one billion USD of capital for EOS projects. We’re amidst onboarding a few critical partners first that will give EOS and this program the world-class credibility it deserves.*

* #### EOS roadmap

  * The project was started in Q1 2017, it was publicly announced in May 2017.
  * Right now we have a MVP stage called *EOS Dawn*. You can run a standalone EOS node and play with smart-contracts using command line tools. Public testnet will be launched in December.
  * By the end of the year an EOS version featuring all major functionalities will be released. Only single-threaded execution will be supported at this stage.
  * Q1 & Q2 2018 will be devoted to testing and building development tools & documentation. During this phase you can starting building apps running on the testnet.
  * The EOS blockchain goes live in June 2018. Initially the assumption was that it would be launched as single-threaded and parallel execution would be added in the next stage, but according to the latest news parallel execution is going to be right from the start.

* #### Wrap up

    * What sets EOS aside, is not just the technology. It's actually the way it's going to operate and the role of tokens in the future of the blockchain. 
    * Ethereum looks like a good proof of concept, a very useful one, as it has shown that there is an actual demand for blockchain-based solutions and smart-contracts. Whereas EOS is extremely business oriented: you can reliably build business on top of it, businesses with predictable cost and businesses which will scale.
    * EOS is an incremental improvement that adds parallelism and generalization to stuff that's already been proven to work. And that's the main difference in approach: the EOS team figured out how to build decentralized applications first and then they started generalizing them, versus attempting to generalize something that you have not even figured out how to build yet.




## ad 6. About Tokenika

* #### What we do?

  * Our focus is on blockchain-based fundraising and digital asset management. Projects like NeuFund, Melonport are Iconomy are the best approximation of the domain we want to be in.

    We believe that just as there has been an ICO frenzy on Ethereum for the last couple of months,  there will be a similar one on EOS. This time by businesses who actually want to build production-ready apps, not prototypes or proofs of concept. Real apps used by real people, i.e. not only blockchain folks.

    We want to be prepared for this happening: businesses wanting to raise funds and investors wanting to risk funds, and then manage their cryptocurrency portfolio in a convenient & secure manner.

  * We are setting up a software house dedicated to building dApps (both on EOS and ETH). We are already experimenting with EOS smart-contracts and already have third-parties manifesting interest in using us to convert their ideas into EOS apps.

  * As far as EOS is concerned, we aim to become one of the 20 block producers (called *witnesses*) once the system goes live.

    How realistic is that? Well, it depends how determined you are. Unless you are a major stakeholder of EOS (which we are not), the only way to do it is via building a strong reputation in EOS community. How do you do that? By doing things which are considered to be beneficial for EOS and its ecosystem. Who is the judge here? EOS community and EOS shareholders. It's similar to an attempt to be elected to the board of directors in a publicly traded company.

    As you can see we've been doing (and will continue to be doing) various things to this end and actually this very presentation is part of the process.

    And obviously to be a viable witness candidate you need to be able to handle the server infrastructure and make it both robust and secure. I guess we can manage that as our main advisor, who prefers to remain anonymous, is already a witness for Steem.

* #### What we need?

  * Contrary to most folks out there, we're not looking for money. We are looking for ways to spend money.
  * Looking for good ideas that can be converted into dApps.
  * Hiring developers with background in C++ and/or ETH smart-contracts.