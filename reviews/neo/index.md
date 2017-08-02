

## NEO is a distributed network for the Smart Economy. Create digital assets and use smart-contracts to make them self-managed.

NEO is the use of blockchain technology and digital identity to digitize assets, the use of smart contracts for digital assets to be self-managed, to achieve "smart economy" with a distributed network.

### Digital Assets

Digital assets are programmable assets that exist in the form of electronic data. With blockchain technology, the digitization of assets can be decentralized, trustful, traceable, highly transparent, and free of intermediaries. On the NEO blockchain, users are able to register, trade, and circulate multiple types of assets. Proving the connection between digital and physical assets is possible through digital identity. Assets registered through a validated digital identity are protected by law.

NEO has two forms of digital assets: global assets and contract assets. Global assets can be recorded in the system space and can be identified by all smart contracts and clients. Contract assets are recorded in the private storage area of the smart contract and require a compatible client to recognize them. Contract assets can adhere to certain standards in order to achieve compatibility with most clients.

### Digital Identity

Digital identity refers to the identity information of individuals, organizations, and other entities that exist in electronic form. The more mature digital identity system is based on the PKI (Public Key Infrastructure) X.509 standard. In NEO, we will implement a set of X.509 compatible digital identity standards. This set of digital identity standards, in addition to compatible X.509 level certificate issuance model, will also support Web Of Trust point-to-point certificate issuance model. Our verification of identity when issuing or using digital identities includes the use of facial features, fingerprint, voice, SMS and other multi-factor authentication methods. At the same time, we will also use the blockchain to replace the Online Certificate Status Protocol (OCSP) to manage and record the X.509 Certificate Revocation List (CRL).

### Smart Contract

The smart contract was first proposed by the cryptographer Nick Szabo in 1994, only five years after the creation of the World Wide Web. According to Szabo's definition: When a pre-programmed condition is triggered, the smart contract will execute the corresponding contract terms. Blockchain technology provides us with a decentralized, tamper-resistant, highly reliable system in which smart contracts are very useful. NEO has an independent smart contract system: NeoContract.

The NeoContract smart contract system is the biggest feature of the seamless integration of the existing developer ecosystem. Developers do not need to learn a new programming language but use C#, Java and other mainstream programming languages in their familiar IDE environments (Visual Studio, Eclipse, etc.) for smart contract development, debugging and compilation. NEO's Universal Lightweight Virtual Machine, NeoVM, has the advantages of high certainty, high concurrency, and high scalability. The NeoContract smart contract system will allow millions of developers around the world to quickly carry out the development of smart contracts. NeoContract will have a separate white paper describing the implementation details.

### Application and Ecosystem

Ecosystem is the vitality of the open source community. In order to achieve the goal of an intelligent economic network, NEO will be committed to the development of its ecosystem, providing mature development tools, improving development of documents, organizing education and training activities, and providing financial support. We plan to support the following NEO-based applications and ecology and to reward improvements to the design of the experience:

🔹 **Node Program**

- A fully functioning Full node PC program
- A light node PC program with a better user experience
- Web / Android / iOS clients that do not need to synchronize with the blockchain
- Hardware wallet

🔹 **Blockchain Explorer**

🔹 **SDK Development Kit**

- support Java / Kotlin, .NET C # / VB, JavaScript / Typescript, Python, Go

🔹 **Smart Contract Compiler and IDE Plugin**

- C# / VB.Net / F#, Visual Studio
- Java / Kotlin, Eclipse
- C / C++ / GO
- JavaScript / TypeScript
- Python / Ruby

🔹 **Decentralized Applications**

- Smart fund
- AI-assisted legal smart contract
- Social networking
- Automated tokens liquidity providers
- Decentralized exchange
- Secure communication protocol
- Data exchange market
- Intellectual property trading market
- Prediction market
- Advertising market
- Hashpower market
- NeoGas market

## NEO Management Model

### Economic Model

NEO has two native tokens, NEO (abbreviated symbol NEO) and NeoGas (abbreviated symbol GAS).

NEO, with a total of 100 million tokens, represents the right to manage the network. Management rights include voting for bookkeeping, NEO network parameter changes, and so on. The minimum unit of NEO is 1 and tokens cannot be subdivided.

GAS is the fuel token for the realization of NEO network resource control, with a maximum total limit of 100 million. The NEO network charges for the operation and storage of tokens and smart contracts, thereby creating economic incentives for bookkeepers and preventing the abuse of resources. The minimum unit of GAS is 0.00000001.

In the creation block of the NEO network, 100 million NEOs are generated, GAS has not yet been generated. 100 million GAS, corresponding to the 100 million NEO, will be generated through a decay algorithm in about 22 years time to address holding NEO. If NEO is transferred to a new address, the subsequent GAS generated will be credited to the new address.

The NEO network will set a threshold by voting to exempt GAS from a certain amount of transfer transactions and smart contract operations to enhance the user experience. When a large amount of spam transactions occur, NeoID can be used to prioritize transactions and smart contracts with qualified identities. Transactions and smart contracts with no qualifying digital identities can get priority by paying GAS.

### Distribution Mechanism

NEO distribution:

NEO's 100 million tokens is divided into two portions. The first portion is 50 million tokens distributed proportionally to supporters of NEO during the crowdfunding. This portion has been distributed.

The second portion is 50 million NEO managed by the NEO Council to support NEO's long-term development, operation and maintenance and ecosystem. The NEO in this portion has a lockout period of 1 year and is unlocked only after October 16, 2017. This portion will not enter the exchanges and is only for long-term support of NEO projects. The plans for it are as below:

🔹 10 million tokens (10% total) will be used to motivate NEO developers and members of the NEO Council

🔹 10 million tokens (10% total) will be used to motivate developers in the NEO ecosystem

🔹 15 million tokens (15% total) will be used to cross-invest in other block-chain projects, which are owned by the NEO Council and are used only for NEO projects

🔹 15 million (15% total) will be retained as contingency

🔹 The annual use of NEO in principle shall not exceed 15 million tokens

GAS distribution:

GAS is generated with each new block. The initial total amount of GAS is zero. With the increasing rate of new block generation, the total limit of 100 million GAS will be achieved in about 22 years. The interval between each block is about 15-20 seconds, and 2 million blocks are generated in about one year.

In the first year (actually 0-200 million blocks), each block will generate 8 new GAS; in the second year (actually the first 200-400 million blocks), each new block will generate 7 GAS and so on. There will be an annual reduction of 1 GAS for the first 8 years until 1 GAS per block is reached; this will be the rate of GAS generation until about 22 years, after the 44 millionth block, GAS total will reach 100 million, thus stopping the generation of GAS from new blocks.

According to this release curve, 16% of the GAS will be created in the first year, 52% of the GAS will be created in the first four years, and 80% of the GAS will be created in the first 12 years. These GAS will be distributed proportionally in accordance with the NEO holding ratio, recorded in the corresponding addresses. NEO holders can initiate a claim transaction at any time and claim these GAS tokens at their holding addresses.

### Governance mechanism

Chain governance: NEO token holders are the network owners and managers, managing the network through voting in the network, using the GAS generated from NEO to utilize the functions in the network. NEO tokens can be transferred.

Off-chain governance: NEO Council consists of the founding members of the NEO project, under which the management committee, technical committee and the secretariat, respectively, are responsible for strategic decision-making, technical decision-making and specific implementation. The NEO Council is responsible to the NEO community for the promotion and development of NEO ecosystem as its primary objective.

## NEO technology implementation

### Consensus mechanism: DBFT

DBFT is called the Delegated Byzantine Fault Tolerant, a Byzantine fault-tolerant consensus mechanism that enables large-scale participation in consensus through proxy voting. The holder of the NEO token can, by voting, pick the bookkeeper it supports. The selected group of bookkeepers, through BFT algorithm, reach a consensus and generate new blocks. Voting in the NEO network continues in real time, rather than in accordance with a fixed term.

DBFT provides fault tolerance of f = ⌊ (n-1) / 3 ⌋ for a consensus system consisting of n consensus nodes. This fault tolerance also includes both security and availability, resistance to general and Byzantine failures, and is suitable for any network environment. DBFT has good finality, meaning that once confirmations are final, the block can not be bifurcated, and the transaction will not be revoked or rolled back.

In the NEO DBFT consensus mechanism, taking about 15 to 20 seconds to generate a block, the transaction throughput is measured up to about 1,000TPS, which is excellent performance among the public chains. Through appropriate optimization, there is potential to reach 10,000TPS, allowing it to support large-scale commercial applications.

DBFT combines digital identity technology, meaning the bookkeepers can be a real name of the individual or institution. Thus, it is possible to freeze, revoke, inherit, retrieve, and effect judicial decisions on them. This facilitates the registration of compliant financial assets in the NEO network. The NEO network plans to support such operations when necessary.

### Smart contract system: NeoContract

NEO's smart contract system consists of three parts:

**NeoVM - Universal Block Chain Virtual Machine:**

NeoVM is a lightweight, general-purpose virtual machine whose architecture is very close to the JVM and .NET Runtime, similar to a virtual CPU that reads and executes instructions in the contract in sequence, performs process control based on the functionality of the instruction operations, logic operations and so on. It has a good start-up speed and versatility, is very suitable for small programs such as smart contracts, can also be ported to non-blockchain of the scene, or integrated with the IDE to provide an optimal development experience. NeoVM's functionality can be extended, like introducing a JIT (real-time compiler) mechanism, thereby enhancing the efficiency of the implementation.

**InteropService - Interoperable Services:**

Used to load the blockchain ledger, digital assets, digital identity, persistent storage area and other underlying services. They are like virtual machines that are provided for virtual machines, enabling smart contracts to access these services at run time to achieve some advanced functionality. Through this low-coupling design, **NeoVM can be ported to any blockchain or even non-blockchain system used, increasing the utility of the smart contracts.**

**DevPack - Compiler and IDE plugin:**

DevPack includes the high-level language compiler and the IDE plug-in. Because NeoVM's architecture is very similar to JVM and .NET Runtime, the compilers in DevPack can compile Java byte code and .NET MSIL into NeoVM's instruction set. Java / Kotlin, C# developers do not need to learn new languages and will be able to immediately start developing smart contracts in VS, Eclipse and other familiar IDE environments. **This greatly reduces the learning curve for developing smart contracts, allowing us to easily build a vibrant community around NeoContract.**

NeoContract can create a smart contract call tree through static analysis before running a smart contract. **Through the deterministic call tree, the NEO node can dynamically fragment the smart contract to achieve theoretically unlimited expansion**, which overcomes the "jamming effect" caused by the static fragmentation of other block chain systems.

### Cross-chain interoperability agreement: NeoX

NeoX is a protocol that implements cross-chain interoperability. NeoX is divided into two parts: "cross-chain asset exchange protocol" and "cross-chain distributed transaction protocol."

**Cross-chain asset exchange agreement:**

NeoX has been extended on existing double-stranded atomic asset exchange protocols to allow multiple participants to exchange assets across different chains and to ensure that all steps in the entire transaction process succeed or fail together. In order to achieve this function, we need to use NeoContract function to create a contract account for each participant. If other blockchains are not compatible with NeoContract, they can be compatible with NeoX as long as they can provide simple smart contract functionality.

**Cross-chain distributed transaction protocol:**

Cross-chain distributed transactions mean that multiple steps of a transaction are scattered across different blockchains and that the consistency of the entire transaction is ensured. This is an extension of cross-chain asset exchange, extending the behavior of asset exchange into arbitrary behavior. In layman's terms, NeoX makes it possible for cross-chain smart contracts where a smart contract can perform different parts on multiple chains, either succeeding or reverting as a whole. This gives excellent possibilities for cross-chain collaborations and we are exploring cross-chain smart contract application scenarios.

### Distributed Storage Protocol: NeoFS

NeoFS is a distributed storage protocol that utilizes Distributed Hash Table technology. NeoFS indexes the data through file content (Hash) rather than file path (URI). Large files will be divided into fixed-size data blocks that are distributed and stored in many different nodes.

The main problem with this type of system is the need to find a balance between redundancy and reliability. NeoFS plans to solve this contradiction by means of token incentives and the establishment of backbone nodes. Users can choose the reliability requirements of the file. Files with low reliability requirements can be stored and accessed for free or almost free. High reliability requirements will be provided by the stable and reliable backbone nodes.

NeoFS will serve as one of the InteropService interoperability services under the NeoContract system, enabling smart contracts to store large files on the blockchain and set access for those files. In addition, NeoFS can be combined with digital identity so that digital certificates used by digital identities can be assigned, sent, and revoked without needing a central server to manage them. In the future, the old block data can be stored in NeoFS, so that most of the full nodes can release the old data for better scalability and at the same time, ensure the integrity of historical data.

### Anti-quantum cryptography mechanism: NeoQS

The emergence of quantum computers creates a major challenge to RSA and ECC-based cryptographic mechanisms. Quantum computers can solve the large number of decomposition problems (which RSA relies on) and the elliptic curve discrete logarithm (which ECC relies on) in a very short time. NeoQS (Quantum Safe) is a lattice-based cryptographic mechanism. At present, quantum computers do not have the ability to quickly solve the Shortest Vector Problem (SVP) and the Closest Vector Problem (CVP), which is considered to be the most reliable algorithm for resisting quantum computers.

## Summary

NEO is a distributed network that combines digital assets, digital identities and smart contracts. The NEO system will use DBFT, NeoX, NeoFS, NeoQS and many other original technologies, as the infrastructure for the intelligent economy of the future.

<span style="color:silver;font-size:11px">Source: [docs.neo.org](http://docs.neo.org/en-us/)</span>

---

## Collaborations

### **Alibaba**

In October of 2016, Jack Ma from Alibaba announced that it would use a blockchain called the Law Chain, with development partners Microsoft and China’s [open-source blockchain Antshares](https://www.antshares.org/), as an email repository for its Ali Cloud platform. By backing up its email and cloud services on the Law Chain, Alibaba will enable large scale adoption of digital evidence and emails in Chinese courts.

This has significant implications for Chinese society. Ali Cloud is one of China’s top providers of computing services, domain services, emails, network security and big data analysis. With its data and emails preserved for judicial departments as courtroom evidence, this may be the first instance of blockchain being utilized by a state judiciary.

### **Microsoft**

The Antshares team has teamed-up with Microsoft to work on R&D, specifically with their Azure PaaS. The team will be working on ‘The Legal Chain’, a consortium chain developed by Fadada (China’s leading online legal service firm), Onchain (a for-profit entity created by the Antshares team), and Microsoft Azure that provides a blockchain-powered digital legal evidence repository.

The team is also working with Microsoft in several other confidential initiatives like direct utilization of the Antshares blockchain. According to Da Hongfei, the creator of Antshares, their blockchain project will enable interoperability in the future that is increasingly heading towards a multi-chain environment.

### **WINGS**

Not only that, Antshares has also partnered with WINGS, a decentralized platform to create, join and manage decentralized autonomous organizations (DAO).

WINGS combines the ideas of crowdfunding with swarm intelligence decision-making through decentralized forecast markets into a project funding and governance platform easily accessible to anyone with a smartphone.

Antshares is a decentralized network protocol based on blockchain technology to digitalize assets or shares, and consummate financial business transactions such as registration, issuance, exchange, settlement, and payment through the Antshares peer-to-peer network. The partnership will advance the cryptocurrency ecosystem and establish new standards for safe funding of projects and companies.

## Should I Buy Antshares as Part of My Investment Portfolio?

(+) Chinese product, Chinese is very patriotic on their own projects, so they will more likely support their own Ethereum version than the original one.

(+) Smart Contracts 2.0: A way to write smart contracts in any of the popular programming languages (C#, Javascript, and more). There is no need to learn a new language to be part of the development.

(+) Partnership with big brands such as Alibaba, WINGS and Microsoft. That boost the confidence of the public and attract more collaborations with other companies.

(+) Antshares Introduces Beta Smart Contracts 2.0 in May 2017. The concept of smart contracts has been well received by developers all over the world. Since the underlying technology of smart contracts has not been seen by the general public, Antshares wants to change all of that moving forward.

<span style="color:silver;font-size:11px">Source: [managingyourfinance.com](https://managingyourfinance.com/what-is-antshares-should-i-buy-antshares-where-to-buy-antshares)</span>

---

## Is NEO 'China's Ethereum'?

NEO has been called “China’s Ethereum”. The Western market first collectively learned about Antshares, a smart contract and decentralized application (dApp) platform, just ahead of the company’s rebrand to ‘NEO’ – which is Greek for “newness”, novelty and youth. That merely one exchange offers bitcoin-NEO trades has led to a bottleneck in supply. Prices skyrocketed in the weeks ahead of the rebrand. Antshares’ ICO was in the fall of 2016.

NEO development began in 2014 and the blockchain-startup ONCHAIN is overseeing its enterprise version. Already the platform offers more languages than Ethereum supports. NEO’s partners include crowdfunding platform WINGS and multinational technology corporation Microsoft. [Reports](https://siliconangle.com/blog/2016/10/20/onchain-partners-with-alibaba-for-blockchain-powered-email-evidence-repository/) last year of a partnership between Alibaba and the former AntShares were false, though the companies have worked together.

NEO’s collaboration with Wings is for research and development purposes. With Ali Cloud and ONCHAIN, NEO is working on a proof of existence e-mail repository.

That [NEO](http://www.neo.org/) representatives seemingly have the okay from the government – having attended a government-sponsored industry conference – could bode well for the blockchain project. 

## NEO Price History as Antcoin

The token price, still trading under its former ticker ‘ANC’ or ‘ANS’ across the web on this article’s publish date, and until the rebrand is complete in the third quarter of 2017, skyrocketed particularly from June 19-20. The platform increased from 1.65 USD on June 15th to 10 USD at the time of writing on June 20. It then corrected and currently sits at just shy of 7 USD, according to CoinMarketCap. Antshares’ all-time high sits at 11.79 USD.

The decentralized smart contract platform’s first price history, according to CoinMarket Cap, started this past fall. The project’s native token started trading at a price of 55 cents before settling between approximately 10 cents and 30 cents. ANC trended south until the end of October 2016, when it reached a nadir of 8 cents. The price then skyrocketed to 31 cents. After a quick price increase, the price drifted downwards until March 2017 when it, along with much of the crypto-asset complex, increased in value.

Per the rebrand, not only does Antshares become NEO, but Antcoin (ANC) becomes ‘GAS’. “So, it is no longer a ‘dividend interest’ sort of asset, but a utility sub-token for network functionalities,” a NEO community member told Hacked.com.

## Under the Hood

NEO smart contracts are based on NEO’s Virtual Machine, which is similar to Ethereum’s Virtual Machine. NEO plans to soon release its “Smart Economy” platform, which has also been termed “Smart Contracts 2.0”.

NEO is designed to solve the same problems as Ethereum. NEO’s incorporation of [sharding](https://en.wikipedia.org/wiki/Shard_(database_architecture)) and [concurrency](https://www.youtube.com/watch?v=CWuCQGvuYo8) in its computer science model solves scalability problems. Ethereum has yet to make such changes to better scale that smart contract and dApp platform.

## Delegated Byzantine Fault Tolerance

By using Delegated Byzantine Fault Tolerance (dBFT) for its blockchain operations – a consensus method proponents claim offers better security for blockchains – NEO places itself in the company of the well-known blockchain project Hyperledger, and the lesser-known Stellar. “Specialized bookkeeping nodes” reach consensus via “delegated voting” per NEO’s dBFT model. It takes a two-thirds vote for approval of a current copy of a blockchain.

“After investigating and studying the crypto-industry and blockchain technologies for several years, we came to the conclusion that the delegated Byzantine Fault Tolerance alternative (or dBFT) is best suited for such a system,” Erik Iz, co-founder and core developer at Antshares, stated on BitcoinTalk. “It provides swift transaction verification times, de-incentivises most attack vectors and upholds a single blockchain version with no risk of forks or alternative blockchain records emerging – regardless of how much computing power, or coins an attacker possesses.”

## Nest Smart Fund

With the rebrand in NEO’s past, the team is looking forward to expanding its western-focused marketing efforts, a NEO community member told Hacked.com. Moreover, it’s partnered on a “do over” for the cryptocurrency community.

“Nest is a whole new form of smart fund written in Antshares smart contracts,” writes NEO about its new ‘DAO’ style fund called [Nest Fund,](http://www.nestfund.io/) which uses NEO smart contract technology.

The DAO, or ‘decentralized autonomous organization’, had set out to become a decentralized venture capital fund based on Ethereum’s smart contract code. It failed.

NEO adds about its attempt at a similar fund: “Nest aims to, with the power of blockchain, eliminate and neutralize problems like high threshold, high risk, low efficiency and moral risks. Participants invest, manage and exit with smart contracts instead of application to certain organizations. Antshares’ Blockchain enables everyone to join the Nest, with a 0 threshold and 100% transparency, with a safe and free exit option at any given time.”

For a cryptocurrency community that likes to be right – they told you so about Bitcoin, after all – Nest could garner serious interest for users looking to make a point, and prove the ideas behind crypto right.

## Numerous Blockchain Products

Nest Fund isn’t the only blockchain-based service or product offered by NEO. Other than its parent, ONCHAIN, NEO leads projects including blockchain-based browsers,  a web-based crypto-asset wallet, as well as an online crowdfunding fund that is not the aforementioned Nest. The team also partnered with Microsoft Azure to bring blockchain technology to the server experience. This project is similar to partnerships pioneered by [Azure](https://azure.microsoft.com/en-us/solutions/blockchain/) in the west.

## The Verdict

Antshares is available on just five exchanges currently, and that limits the amount of buying demand for ANC. Just a single exchange buys and sells ANC for Bitcoin. Now, as many westerners learn of NEO for the first time, the demand will only increase.

But a lack of information available in English about NEO could slow demand. When NEO’s implementation of blockchain technology receives increasing press in the English-speaking world – and it likely will considering its corporate partners – there could be further price implications. The crypto-asset is currently the 23rd largest, according to Coin Market Cap. On CoinCap.io, it is the 21st largest.

Only time will tell with NEO, but there are lots of intriguing projects in the works at the blockchain company, including authentication work with Chinese authorities to map real-world assets with smart contracts. The company also has numerous patents, including ones for cross-chain interoperability. It’s partnered with numerous blockchain projects, like Bancor, Agrello, Coindash and Binance.

Due to NEO’s corporate partners –  among whom are included Microsoft, etc. –  and its under the radar Ethereum-esque functionality, we give the project a 7.75 out of 10.

<span style="color:silver;font-size:11px">Source: [hacked.com](https://hacked.com/token-analysis-neo-formerly-antshares-chinas-ethereum/)</span>

---

## What does Antshares offer?

Antshares bridges the gap between digital and traditional financial ecosystems by allowing the creation of digital assets and conversion of real-world financial assets to virtual ones. People can register, deposit, transfer, trade and even make settlement of digital assets over Antshares network.

##### E-contracts and Fiat Currency Support

Activities on [Antshares network are registered as e-contracts](https://www.antshares.org/) on the underlying distributed ledger. These e-contracts can be used to maintain a record of transactions and rights associated with digital assets like equities, claims, securities, financial contracts, credit points, bills and currencies.

##### User-controlled Identity Authentication

Antshares platform closely matches with the existing structures to ensure ease of migration from conventional documentation procedures to digital ones.

##### Joint Bookkeeping

Antshares deviates from the existing bookkeeping norms set by the likes of Bitcoin, Ethereum and Bitshares by allowing joint book-keeping where more than one person is involved in the process.

##### Antshares dBFT Consensus Algorithm

The use distributed Byzantine Fault Tolerance (dBFT) Consensus Algorithm increases the fault tolerance of the distributed ledger. It allows Antshares to separate bookkeeping nodes from ordinary listening nodes that match orders and generate blocks to be added later on to the bookkeeping node. It also makes the platform more energy and time efficient.

##### Division of Labor of Nodes

The blockchain network in Antshares is further optimized by the clear demarcation of tasks to prevent unnecessary exploitation of members’ storage space and processing power. The bookkeeping nodes and full nodes are operated and maintained by service providers.

##### Scalability

The low latency and high throughput architecture of Antshares, brought about by the use of weak trust based consensus mechanism will allow unlimited scalability of the network. With a block interval of 15 seconds, Antshares blockchain is capable of processing tens of thousands of requests per minute.

##### Superconducting Transactions

In order to cut the processing time and power, the order book-keeping and order matching is delegated to a secondary layer of the blockchain instead of core bookkeeping nodes. The use of multiple layers offers [greater control over transactions to Antshares users](https://www.antshares.org/). During a transaction, orders are matched by the secondary layer of the blockchain, which then sends it to the primary book-keeping nodes for clearance and settlement. Users can decide to cancel a transaction by launching a double spend attack before the transaction is cleared by book-keeping nodes.

<span style="color:silver;font-size:11px">Source: [jackobian.com](http://www.jackobian.com/threads/antshares-review-platform-with-great-stability.64140/)</span>