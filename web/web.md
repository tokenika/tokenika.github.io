# What is EOS?

[EOS](https://eos.io/) is the blockchain for building commercial scale decentralized applications that are indistinguishable from centralized alternatives.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@stellabelle/re-dantheman-re-kyriacos-re-dantheman-re-eosio-introducing-the-eos-blog-on-steemit-20170514t144829951z), by Dan Larimer, May 2017</span>

The EOS.IO software introduces a new blockchain architecture designed to enable vertical and horizontal scaling of decentralized applications. This is achieved by creating an operating system-like construct upon which applications can be built. The software provides accounts, authentication, databases, asynchronous communication and the scheduling of applications across hundreds of CPU cores or clusters. The resulting technology is a blockchain architecture that scales to millions of transactions per second, eliminates user fees, and allows for quick and easy deployment of decentralized applications.

<span style="color:silver;">Source: [github.com](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md), Technical White Paper, June 2017</span>

---

# Why EOS?

Six reasons why choosing EOS makes sense:

#### 1. Ogromna wydajność

Podczas gdy inne rozwiązanie wymagają drugiej warstwy procesowania, aby być w stanie obsłużyć popyt na procesowanie transakcji w warunkach produkcyjnych (czyli odpowiednik Lightening Network w Bitcoinie albo Plasmy w Ethereum), EOS osiąga gigantyczną wydajność w swojej warstwie podstawowej. Wynika to z następujących powodów:

* DPOS daje stałą liczbę producentów bloków. Dzięki temu interwały między blokami są na poziomie 3 sekund (a przy lepszej infrastrukturze serwerowej mogą być jeszcze krótsze). Warto dodać że mimo tej skończonej liczby producentów bloków, DPOS jest najbardziej zdecentralizowanym systemem jaki istnieje - oczywiście jeśli zastosujemy racjonalnie uzasadnioną metodę pomiaru stopnia zdecentralizowania. [Tutaj](http://bytemaster.github.io/article/2015/01/13/Decentralization-of-Nxt-vs-BitShares/) jest to dokładniej wyjaśnione.
* Blockchain EOSa (podobnie jak BitShares i Steem) stosuje podejście *consensus over events* zamiast standardowego *consensus over state*. W wyniku tego wprawdzie dłużej trwa uruchomienie nowego node'a, ale w zamian szybciej działa bieżące procesowanie transakcji. Jest to bardzo korzystny trade-off, bo uruchamianie nowego node'a zdarza się rzadko, a wydajne procesowanie transakcji potrzebne jest non-stop. [Tutaj](https://steemit.com/eos/@iang/the-message-is-the-medium) jest to dokładniej wyjaśnione.
* Architektura EOSa od samego początku została tak zaprojektowana żeby możliwe było procesowanie wielowątkowe. Póki co żaden inny blockchain tego nie potrafi. Więcej szczegółów [tutaj](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#deterministic-parallel-execution-of-applications).
* EOS umożliwia procesowanie podzbioru transakcji, tj. tylko tych którymi dany node jest zainteresowany - tym samym możliwe jest ignorowanie wszystkich pozostałych transakcji. Więcej szczegółów [tutaj](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#partial-evaluation-of-blockchain-state).

#### 2. Znacznie szerszy kontekst

EOS traktuje kwestię smart-kontraktów znacznie szerzej niż Ethereum. W założeniu EOSa błędy w kodzie smart-kontraktów są nieuniknione, więc zostały wbudowane w blockchain mechanizmy, które adresują ten problem: konstytucja, arbitraż w przypadku sporów, głosowanie w zakresie decyzji. Gdyby przypadek *The DAO* wydarzył się na EOSie, byłaby klarowna procedura rozwiązania tego problemu. Widać w tym dużą mądrość i dobre wyczucie potrzeb poważnych biznesów: posiadanie z góry zdefiniowanej drogi ewakuacyjnej w przypadku katastrofy jest fundamentalnie istotne.

#### 3. Kompletny system operacyjny

EOS pozycjonuje się nie jako rozproszony komputer lecz bardziej jako rozproszony system operacyjny. Oznacza to że na poziomie blockchaina dostępne są wszystkie funkcjonalności które są niezbędne dla każdej zaawansowanej aplikacji, np. databases, account permissions, account recovery, scheduling, authentication, inter-app communication. Czyli developerzy smart-kontraktów EOSa mają za zadanie zakodować tylko to co jest unikalne dla danej aplikacji, podczas gdy cała reszta jest dostarczona na poziomie samego blockchaina.

#### 4. Web Assembly

Web Assembly is an emerging industry standard backed by Microsoft, Google, and Apple. The goal of this standard is to make it possible to run untrusted high-performance code in your browser. [Web Assembly is a game changer](https://medium.com/mozilla-tech/why-webassembly-is-a-game-changer-for-the-web-and-a-source-of-pride-for-mozilla-and-firefox-dda80e4c43cb), it will enable high performance web applications such as video and image editing and games. More details are available [here](https://steemit.com/eos/@dantheman/web-assembly-on-eos-50-000-transfers-per-second).

#### 5. Brak opłat transakcyjnych (z punktu widzenia użytkownika końcowego)

EOS wychodzi z założenia, że najważniejszym kryterium są wymagania biznesowe a nie ograniczenia technologii. Z punktu widzenia biznesu nie ma racji bytu paradygmat, w którym użytkownik końcowy jest zmuszony do płacenia za sam fakt interakcji z daną aplikacją, tak jak jest to teraz standardem w świecie kryptowalut. Aplikacja taka jak Steem nie mogłaby istnieć w takim modelu. EOS proponuje rozwiązanie, które powszechnie funkcjonuje w normalnym świecie: problem finansowania danego biznesu jest po stronie dawcy usługi (tj. twórcy smart-kontraktu) a nie po stronie jego klienta - ten defaultowo powinien mieć dostęp darmowy (no chyba że twórca smart-kontraktu postanowi inaczej - ważne jest żeby był możliwy wybór dowolnej strategii).

#### 6. Koncepcja zweryfikowana w praktyce

Wszystkie inne niż EOS platformy smart-kontraktowe są budowane jako rozwiązanie generyczne. Czyli zaczynamy od abstrakcji a celem jest zbudowanie przestrzeni do implementacji konkretnych aplikacji. EOS idzie w odwrotnym kierunku: od implementacji do abstrakcji. Twórcy EOSa mają w swoim dorobku dwa działające blockchainy (BitShares i Steem), które w sumie procesują więcej transakcji niż Bitcoin i Ethereum. Tym samym EOS jest uogólnieniem dwóch konkretnych (i bardzo różnych) implementacji. Daje to duże prawdopodobieństwo, że EOS będzie czymś co rzeczywiście sprawdza się w praktyce.

---

# Known limitations

While we are not hinding our strong commtiment for EOS, stil we aim to remain objective. Below are there are things you need to be aware of:

* When compared to Ethereum, at the current stage EOS is not widely popular among developers and blochchain start-ups. There is still a lot that needs to be done in this area in order to raise awareness and atract businesses to experiment with EOS. 
* EOS is not live yet. The testnet is about to be launched, and the ETA for live version is June 2018.

Odnośnie terminu live, informację tę warto interpretować następująco: Steem powstał z kodu BitShares w ciągu 3 miesięcy, co oznacza że zespół deweloperów EOSa działa bardzo sprawnie. Długi okres testów EOSa sugeruje że priorytetem jest jakość i że w momencie pójścia live EOS prawdopodobnie będzie bardzo zaawansowanym i stabilnym systemem. 

---

# Roadmap

##### Phase 1 - Minimal Viable Testing Environment - Summer 2017

- Standalone Node
- Native Contracts
- RPC Interface
- Command line Tools
- Basic Developer Documentation

##### Phase 2 - Minimal Viable Test Network - Fall 2017

- P2P Network Code
- WASM Sanitation & CPU Sandboxing
- Resource Usage Tracking & Rate Limiting
- Genesis Import Testing
- Interblockchain Communication

##### Phase 3 - Testing & Security Audits - Winter 2017, Spring 2018

- Develop Example Applications
- Bounties for Successfully Attacking Network
- Language Support
- Documentation & Tutorials

##### Phase 4 - Parallel Optimization - Summer / Fall 2018

##### Phase 5 - Cluster Implementation - The Future

<span style="color:silver;">Source: [github.com](https://github.com/EOSIO/Documentation/blob/master/Roadmap.md), June 2017</span>

---

# Resources

#### Technical White Paper

The EOS.IO software introduces a new blockchain architecture designed to enable vertical and horizontal scaling of decentralized applications. This is achieved by creating an operating system-like construct upon which applications can be built.

<span style="color:silver;">Source: [github.com](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md), June 2017</span>

#### EOS - An Introduction by Ian Grigg

This paper outlines the context, vision and software architecture underlying EOS, which we are building to serve a broad and diverse group of users with smart business.

<span style="color:silver;">Source: [iang.org](http://iang.org/papers/EOS_An_Introduction.pdf), by Ian Grigg, July 2017</span>

#### Introduction to EOS: the Epic (blockchain) Operating System

EOS is a consensus blockchain operating system that provides databases, account permissions, scheduling, authentication, and internet-application communication to massively improve the efficiency of smart business development that uses parallelization to make possible blockchain scalability to millions of users and millions of transactions per second.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@trogdor/introduction-to-eos-the-epic-blockchain-operating-system), by trogdor, May 2017</span>

#### EOS Shanghai Meetup July 2017

Brendan Blumer, Ian Grigg and Michael Cao speak during a Shanghai Meetup in July 2017.

<span style="color:silver;">Source: [youtube.com](https://www.youtube.com/watch?v=HUA52v-a2TA), July 2017</span>

#### EOS Presentation from NY Consensus 2017

Daniel Larimer introduces EOS.

<span style="color:silver;">Source: [youtube.com](https://www.youtube.com/watch?v=MUZWZj1pu94), May 2017</span>

#### The EOS ICO for Dummies!

The purpose of this post is primarily to focus on issues related to the Initial Coin Offering (ICO) of EOS , and not on specifics of EOS itself. 

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@trogdor/the-eos-ico-for-dummies), by @trogdor, June 2017</span>

---

# Concept blog

#### Who Should Control A Blockchain?

Recently the topic of voting and control has been discussed by multiple blockchain projects. EOS, Ethereum, Bitcoin, and others all agree that blockchains must be controlled by voting, but who should do the voting?

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/who-should-control-a-blockchain), by Brendan Blumer, August 2017</span>

#### Logically Consistent Principles for Token Distributions

The EOS Token distribution has been designed to hopefully create a distribution that is widely perceived to be fair based upon what we believe to be logically consistent principles.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/logically-consistent-principles-for-token-distributions), by block.one, June 2017</span>

#### What could a blockchain Constitution look like?

Traditional platforms such as Facebook and Twitter have a terms of service that define acceptable behavior of users. These terms of service create a hub and spoke model where Facebook and Twitter are the hub and the users are the spokes. A decentralized platform needs to have a peer-to-peer terms of service.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dantheman/what-could-a-blockchain-constitution-look-like), by Dan Larimer, June 2017</span>

#### While A Constitution For A Blockchain May Seem Unusual, It Will Make Early Project Development Much Easier And Result In A More Responsive Platform.

While a blockchain constitution can be compared to the terms of service that many websites use, the main advantage of utilizing a constitution is the ability to make necessary changes efficiently.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@cryptofreedom/while-a-constitution-for-a-blockchain-may-seem-unusual-it-will-make-early-project-development-much-easier-and-result-in-a-more), by @cryptofreedom, June 2017</span>

#### On a Principled Approach to Blockchain Governance - 7 Requirements

One of the things that I learnt in the CAcert adventure was that governance was critical to the safe operation of large communities. How large is large ... is a question of much debate, but to put it bluntly, this is needed beyond say a 2 digit size, which I’ve always seen as around 30, but certainly well before Dunbar’s number of 150

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@iang/on-a-principled-approach-to-blockchain-governance-7-requirements), by Ian Grigg, May 2017</span>

---

# Business blog

#### Statement Regarding the SEC’s Report on The DAO

Since we have received a number of requests to provide our reaction to the SEC’s recent report in relation to The DAO, we would like to state for the record that we are of the opinion that the SEC’s report does not affect the EOS ERC-20 compatible token (the “EOS tokens”) distribution on the Ethereum blockchain

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/block-one-statement-regarding-the-sec-s-report-on-the-dao), by Brendan Blumer, August 2017</span>

#### An Update from Block.one CEO, Brendan Blumer

We appreciate the healthy skepticism and will always do our best to clarify misunderstandings. EOS is comprised of a robust community and backed by many of the the biggest influencers in the space - this is something we don't take for granted and would never compromise!

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/an-update-from-block-one-ceo-brendan-blumer), by Brendan Blumer, August 2017</span>

#### A Recap: EOS Headlines London Fintech Week 2017

This year, an estimated 4,000 delegates from over 50 countries came together for London Fintech Week 2017 to hear from the world's leading experts on current and upcoming trends, challenges, and technology in the Fintech sector.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eosevents/@eosio/a-recap-eos-headlines-london-fintech-week-2017), by block.one, August 2017</span>

#### Coindesk Libels Dan Larimer

Earlier this week Coindesk published its first story covering EOS, written by Aaron Stanley. Considering that EOS was one of the sponsors of Consensus 2017, it was surprising to see that the coverage of EOS was more negative than I would have expected.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@belerophon/coindesk-libels-dan-larimer), by @belerophon, June 2017</span>

#### Shedding some light on the EOS Token Purchase Agreement

I ABSOLUTELY agree with everyone losing their minds at the Purchase Agreement. It appears to be madness and it says black on white that we are buying useless crap. What I’m saying here is WHY it is written like that. In a nutshell: Governments make everything financial illegal.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@cob/shedding-some-light-on-the-eos-token-purchase-agreement), by @cob, June 2017</span>

#### My Approach to Acquiring EOS Tokens

I've spent the past couple of weeks figuring out my approach to get the most cheap EOS tokens as possible, quickly realising there's no way to determine if the price is okay from one day to the next with its pro-rated distribution mechanism.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@kevinwong/my-approach-to-acquiring-eos-tokens), by @kevinwong, July 2017</span>

---

# Technology blog

#### The Message is the Medium

This post introduces what I think is a fundamental flaw in almost all blockchain designs. In brief, it is the emphasis on state as the ‘atomic element’, when we could also build using messages instead. The implications of this are quite severe, but also quite hard to understand because the computer science concepts are a bit inaccessible to the non-CS world.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@iang/the-message-is-the-medium), by Ian Grigg, May 2017</span>

#### Web Assembly on EOS - 50,000 Transfers Per Second

Over the past couple of weeks the EOS development team has pivoted away from the Wren programming language and embraced Web Assembly. Today we would like to update everyone on the progress and initial results we have achieved.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dantheman/web-assembly-on-eos-50-000-transfers-per-second), by Dan Larimer, May 2017</span>

#### DPOS Consensus Algorithm - The Missing White Paper

This is the missing white paper and analysis of delegated proof of stake (DPOS). The goal of this paper is to provide an analysis of why DPOS works and what makes it robust.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper), by Dan Larimer, May 2017</span>

#### Seeking Consensus on Consensus - DPOS or Delegated Proof of Stake and the Two Generals' Problem

Laying down the rails for a high performance financial blockchain-based ecosystem is well understood if controversial because there are a number of approaches - centralised, decentralised, un-permissioned, walled garden.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@iang/seeking-consensus-on-consensus-dpos-or-delegated-proof-of-stake-and-the-two-generals-problem), by Ian Grigg, June 2017</span>

#### Casper as an EOS Contract

I recently reviewed the latest Casper Research Paper in light of an ongoing discussion with Vitalik Buterin over consensus mechinisms. It is my intent to be as objective and practical as possible while recognizing all factors of the greater picture.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/casper-as-an-eos-contract), by Dan Larimer, August 2017</span>

#### EOS.IO software will not suffer from Denial of Service (DOS) attacks like Ethereum

The problem Ethereum faces cannot be solved so long as it retains the current fee model and people insist on doing capped ICOs below market prices on a first-come, first-serve basis. These capped ICOs at below market prices might as well be million dollar giveaways.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dantheman/eos-io-software-will-not-suffer-from-denial-of-service-dos-attacks-like-ethereum), by Dan Larimer, June 2017</span>

#### Blockchains should be designed like massively multiplayer games

In my previous article I made a case about why general purpose blockchains shouldn’t use the UTXO transaction model. Now I will make the case that blockchains should not store state in transactions and I will do so by borrowing lessons learned from massively multiplayer online games.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/blockchain/@dantheman/blockchain-utxo-model-is-a-dead-end-for-general-purpose-applications), by Dan Larimer, April 2017</span>

#### Blockchain UTXO Model is a Dead End for General Purpose Applications

Bitcoin was the first cryptocurrency to introduce the UTXO (Unspent Transaction Output) model for tracking database state. Every Bitcoin transaction consumes (spends) outputs from prior transactions and produces new outputs to be consumed by future transactions.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/blockchain/@dantheman/blockchains-should-be-designed-like-massively-multiplayer-games), by Dan Larimer, April 2017</span>

#### Individuals That Are Skeptical of The Upcoming EOS Project Simply Don't Understand The Fundamental Differences And Advantages That The EOS Network Will Offer.

The amount of attention and investment the upcoming EOS project has already seen makes some individuals skeptical, but to me it validates the demand and faith that investors have in the upcoming smart contract platform.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@cryptofreedom/individuals-that-are-skeptical-of-the-upcoming-eos-project-simply-don-t-understand-the-fundamental-differences-and-advantages), by @cryptofreedom, August 2017</span>

#### Could EOS Become the Most Widely Distributed ICO Ever?

Last month I wrote about the Fear of Missing Out (FOMO) surrounding the EOS ICO. I was wrong. Well, at least I was wrong about my initial short term predictions. I figured, with a year long ICO, the price of EOS would surely drop below the initial 5-day ICO price.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@lukestokes/could-eos-become-the-most-widely-distributed-ico-ever), by @lukestokes, August 2017</span>

#### A Smart Contract Platform Without Transaction Costs or the Need For 'gas' Will Finally Offer Proper Incentive To DApp Developers.

When developers must continually make micro-payments to continue to run and employ their DApps or contracts, price increases make it much less practical to continue to run and develop applications.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@cryptofreedom/a-smart-contract-platform-without-transaction-costs-or-the-need-for-gas-will-finally-make-dapp-development-practical-an), by @cryptofreedom, May 2017</span>

---

# Competition blog

#### How Is EOS different from everything else?

In our community channels we are frequently asked how EOS compares to other blockchain platforms.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/how-is-eos-different-from-everything-else), by block.one, June 2017</span>

#### EOS vs. Ethereum for Dummies!

In this post I will describe some of the differences in technological capabilities and limitations, as well as differences in design philosophies between the EOS and Ethereum platforms.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@trogdor/eos-vs-ethereum-for-dummies), by @trogdor, June 2017</span>

#### Response to Vitalik Buterin on EOS

Vitalik Buterin recently took a question about EOS at the Ethereum Shenzhen Keynote. Today I would like to provide some factual corrections to his claims about EOS.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/response-to-vitalik-buterin-on-eos), by Dan Larimer, August 2017</span>

#### Reponse to Vitalik's Written Remarks

I just recently learned of these remarks from Vitalik on reddit. In these remark's Vitalik brings up the issue of Fees and Voting, both of which I feel deserve to be addressed.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/reponse-to-vitalik-s-written-remarks), by Dan Larimer, August 2017</span>

#### Centralization of Cryptocurrency - Bitcoin, Ethereum, and EOS

This post is food for thought. A small group of individuals all met face to face in New York. This relatively small group decided the future of bitcoin which is now playing-out.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@crypto-investor/centralization-of-cryptocurrency-bitcoin-ethereum-and-eos), by @crypto-investor, August 2017</span>

#### EOS vs. Tezos vs. Tauchain: The Dummies' Simplification Of Possibly The Biggest Blockchain Launches Of 2017...

As the blockchain revolution gains momentum, so has this year brought countless ICOs with mega-hype and mind-blowing multi-million dollar crowdfunding campaigns. It's been a ride. And it's tough to keep up with *everything* coming out. Yet, there are a few projects that stand out amongst the many.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@rok-sivante/eos-vs-tezos-vs-tauchain-the-dummies-simplification-of-possibly-the-biggest-blockchain-launches-of-2017), by @rok-sivante, August 2017</span>

#### Comparison of Ethereum, Hyperledger Fabric and Corda

With this paper, we provide a brief analysis of the most notable differences between the distributed ledger technologies (DLT) Hyperledger Fabric, R3 Corda and Ethereum. Our intention is to give decision makers new to DLT guidance for what use cases Hyperledger Fabric, Corda and Ethereum are most suitable.

<span style="color:silver;">Source: [medium.com](https://medium.com/@philippsandner/comparison-of-ethereum-hyperledger-fabric-and-corda-21c1bb9442f6), by Philipp Sandner, June 2017</span>

---

# Witness blog

#### Storage Costs on Blockchains using EOS.IO Software

The market will naturally and unavoidably imbue monetary properties to tokens created with the EOS.IO software. It will be necessary to implement dynamic pricing on the cost of consuming an additional unit of memory in order to keep prices practical for actual application development. If an EOS.IO based blockchain reaches a 30 billion USD valuation, then 1M USD may be insignificant amount of money for a blockchain able to allocate 1.5 USD billion dollars per year to block producers (5% inflation).

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/storage-costs-on-blockchains-using-eos-io-software), by @eosio, July 2017</span>

#### Heavy duty witness node infrastructure

Witnesses are vulnerable to DDoS attacks. An attacker who knows the network location of your witness node can saturate your uplink to a level that makes you unable to produce blocks on time. Effectively, this means voting the witness out using a network-level attack.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/witness-category/@gtg/heavy-duty-witness-node-infrastructure), by @gtg, July 2017</span>

---

# Developer blog

#### EOS Development Sneak Peek for Very Early Developers

Although the official test network is still in preparation, anyone can create their own test environment on a local node. Please understand things are likely to change; however, not drastically so.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eosdev/@dan/eos-development-sneak-peek-for-very-early-developers), by Dan Larimer, August 2017</span>

#### EOS - Example Exchange Contract and Benefits of C++

This week I have been focused on the API that smart contract developers will use to write contracts. To help facilitate the design of this API I have given myself an example contract to write. This time the example is a little bit more complex than just a currency contract, but a full up exchange between the native EOS currency and an example CURRENCY contract.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/eos-example-exchange-contract-and-benefits-of-c), by Dan Larimer, July 2017</span>

#### Implementing a Hypothetical Currency Application on EOS

Today we are excited to share with you the first sneak peak of how EOS works and how developers build applications.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@eosio/implementing-a-hypothetical-currency-application-on-eos), by Dan Larimer, May 2017</span>

#### EOS - Developer’s Log Stardate 20176.30

This week block.one’s blockchain c++ development team has picked up 4 new members and has been interviewing a few more. The new recruits have already begun making contributions to the code.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/eos-developer-s-log-stardate-20176-30), by Dan Larimer, June 2017</span>

#### EOS - Developer’s Log Stardate 201707.3

Today I met with the team to discuss the challenges of making smart contracts both easy to develop and easy to execute in parallel. If you are familiar with the challenges associated with parallel execution then you know the general rule that all data must be owned by a single thread. In terms of blockchains, that means all accounts need to own their data. Owning data means that no other thread of execution may read or write the data except by asynchronous message passing.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/eos-developer-s-log-starday-201707-3), by Dan Larimer, July 2017</span>

#### EOS - Developer Log, Stardate 201707.7

This week we made great strides toward refining the architecture of EOS and defining the developer API. In particular we have identified a programming model that should enable parallelism while maximizing ease of use and clarity of the code.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/eos-developer-log-stardate-201707-7), by Dan Larimer, July 2017</span>

#### EOS.IO Transaction Structure - Developer's Log, Stardate 201707.9

Today I would like to take a moment to explain the current structure of an EOS.IO transaction so that developers can better understand the concurrency model.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@dan/eos-developer-s-log-stardate-201707-9), by Dan Larimer, July 2017</span>

#### Easy Docker Guide for EOS

My previous post EOS Build Guide on Ubuntu provides instructions to build EOS on native machine. But Docker has many advantages, especially compatibility, so that providing information for Docker users sounds a good idea to me. 

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eoskorea/@clayop/easy-docker-guide-for-eos), by @clayop, 2017</span>

#### EOS Build Guide on Ubuntu

This is a brief guide of building EOS on Ubuntu 16.04 LTS (Google Compute Engine).

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eoskorea/@clayop/eos-build-guide-on-ubunbu), by @clayop, August 2017</span>

#### EOS Build Guide on Mac OS

Here is a brief guide to show you how to build the eos on MacOS Sierra 10.12.6.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eosdev/@skenan/eos-build-guide-on-mac-os), by @skenan, August 2017</span>

#### Interested In Building An EOS Up Single-node Testnet But Don't Have Access To An Ubuntu Desktop?

While an Ubuntu desktop can be installed on programs similar to VirtualBox on your local device, I decided to go with a cloud server because it is much more forgiving.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@cryptofreedom/interested-in-building-an-eos-up-single-node-testnet-but-don-t-have-access-to-an-ubuntu-desktop-i-had-success-deploying-a), by @cryptofreedom, June 2017</span>

#### First Install & Run of EOS on a Blank Ubuntu 16

Here I am showing my steps to run one of the first full nodes of EOS. Unfortunately it just runs on local computer and it doesn't have peer to peer implemented yet, i.e. there is no communication with anybody.

<span style="color:silver;">Source: [steemit.com](https://steemit.com/eos/@deaddy/first-install-and-run-of-eos-on-a-blank-ubuntu-16), by @deaddy, June 2017</span>

---

# Video interviews

#### The New Ethereum Killer Cryptocurrency Called EOS with Dan Larimer

Dan Larimer talks to Jeff Brewick (The Dollar Vigilante) about EOS.

<span style="color:silver;">Source: [youtube.com](https://www.youtube.com/watch?v=8e0tinzPTbY), July 2017</span>

#### Coin Interview with EOS

Dan Larimer talks to the Coin team about EOS.

<span style="color:silver;">Source: [youtube.com](https://www.youtube.com/watch?v=K6uR0A9cC5Y), June 2017</span>

#### Blocktalk Interview with EOS

Dan Larimer talks to the Blocktalk team about EOS.

<span style="color:silver;">Source: [youtube.com](https://www.youtube.com/watch?v=I-X4faugNuI), May 2017</span>

---

# EOS tools

#### EOSscan Service

EOSscan is a service that helps you to purchase [EOS ](http://eos.io/)tokens at the most reasonable price. EOSscan offers you the current price of EOS tokens by analyzing transactions of EOS token purchases on the Ethereum blockchain.

<span style="color:silver;">Link: [eosscan.io](https://eosscan.io/)</span>

---

# About us

*Tokenika* is a group of entrepreneurs based in Poland, aming to contribute to the emerging EOS ecosystem and hopefully become an active EOS witness once the system goes live in Q3 2018.

Our intention is to contribute in the following way:

* aggregate all meaningful information about EOS under one website 
* offer exexutive summaries and comments 
* participate in the EOS testnet
* build useful tools for the EOS ecosystem
* hold public events with the aim to promote EOS in Poland and Europe

---

# Contact

You can reach us at eos@tokenika.io.

