# Plasma: a protocol for executable smart-contracts running atop an existing blockchain

**The proposed Plasma framework will generate scalable autonomous executable distributed code contracts to allow for “potentially billions” of state updates per second on the Ethereum Blockchain.**

**To get around issues of trust that are involved in off-chain multiparty commitments, Buterin and Poon seek to design a system whereby computation occurs off-blockchain but is ultimately enforceable on-chain.**

**According to the whitepaper, Plasma will work similarly to the Lightning Network that Poon helped create, in that it is a series of executable distributed code contracts (EDCCs) running atop an existing blockchain. This ensures enforcement while simultaneously holding funds in a contractstate with a net settlement / withdrawal that is scheduled to take place at a specified later time.**

---

Conceptually, Plasma is very similar to the Bitcoin Core development team’s scaling solution Segregated Witness (SegWit) in the sense that it eliminates unnecessary data in smart contracts and only broadcast merkelized commitments to the public Ethereum blockchain.

By decreasing the amount of information and the size of transactions passed on to the root blockchain of Ethereum, Buterin and Poon explained that the Ethereum Blockchain will be able to process smart contracts and transactions with lower costs and computation.

Plasma is an on-chain scaling solution that scales the Ethereum blockchain by optimizing data passed onto the root blockchain. By doing so, it can reduce gas costs or transaction fees handled by smart contracts and decentralized applications, making the Ethereum ecosystem more flexible for developers and users.

<span style="color:silver;font-size:11px">Source: [cointelegraph.com](https://cointelegraph.com/news/vitalik-buterin-bitcoins-lightning-network-author-reveal-ethereum-scaling-plans-analysis)</span>

---

Plasma is a proposed framework for incentivized and enforced execution of smart contracts which is scalable to a significant amount of state updates per second (potentially billions) enabling the blockchain to be able to represent a significant amount of decentralized financial applications worldwide. These smart contracts are incentivized to continue operation autonomously via network transaction fees, which is ultimately reliant upon the underlying blockchain (e.g. Ethereum) to enforce transactional state transitions.

We propose a method for decentralized autonomous applications to scale to process not only financial activity, but also construct economic incentives for globally persistent data services, which may produce an alternative to centralized server farms.

As only merkleized commitments are broadcast periodically to the root blockchain (i.e. Ethereum) during non-faulty states, this can allow for incredibly scalable, low cost transactions and computation. Plasma enables persistently operating decentralized applications at high scale.

<span style="color:silver;font-size:11px">Source: [plasma.io](http://plasma.io)</span>

---

It’s similar, in many ways, to the Lightning Network as far as the concept is concerned, but it requires no modifications of ethereum’s blockchain, you don’t have to be online to receive a transaction and it works not just for simple transactions but for smart contracts too.

<span style="color:silver;font-size:11px">Source: [trustnodes.com](http://www.trustnodes.com/2017/08/10/plasma-opens-scalability-race-ethereum-blockchains-within-blockchains)</span>

---

A working draft of *Plasma: Scalable Autonomous Smart Contracts*, a [whitepaper](http://plasma.io/plasma.pdf) by Ethereum founder Vitalik Buterin and co-author of the [Lightning Network](https://lightning.network/) whitepaper Joseph Poon, was released August 10, 2017. The paper lays out a plan to massively scale forward the number of transactions per second that the Ethereum blockchain is capable of processing.

The proposed Plasma framework may enable the Ethereum blockchain (or any other blockchain it integrates with) to advance dramatically. A number of features come together to make this possible, and the protocol itself draws upon the integrations of tools such as proof-of-stake(PoS), Nakamoto Consensus (widely referred to as proof-of-work), a cluster scaling solution called MapReduce, and an incentivized structure to deter byzantine behavior by participants. These attributes coalesce in a manner which allows smart contracts, or executable distributed code contracts, to become scalable. Fraud proofs are used to manage data that is recorded for validation purposes, reducing the load on the network. As per the draft, "As only merkleized commitments are broadcast periodically to the root blockchain (i.e. Ethereum) during non-faulty states, this can allow for incredibly scalable, low-cost transactions and computation. Plasma enables persistently operating decentralized applications at high scale."

There is a lot more to the protocol which is still in a draft form, and must be tested and further developed. A great deal of time, effort, and code will go into integrating the Plasma platform atop existing blockchain protocols. Once the obstacle of scaling Ethereum to billions of public and private transactions  is overcome, there’s no telling how much value will be enjoyed by the ecosystem at large.

<span style="color:silver;font-size:11px">Source: [ethnews.com](https://www.ethnews.com/vitalik-buterin-and-joseph-poon-produce-scalability-solution-the-plasma-framework)</span>

---

Similar to the Lightning Network, Plasma is a series of contracts which runs on top of a root blockchain (i.e. the Mainnet Ethereum blockchain). The root network contract processes only tiny amount of commitments from child blockchains that are able to do an incredibly large amount of computations in most cases. Commitments are broadcasted periodically to the root blockchain from the child. One can view the root blockchain as the Supreme Court from which all subordinate courts derive their power.

<span style="color:silver;font-size:11px">Source: [medium.com](https://medium.com/chain-cloud-company-blog/plasma-in-10-minutes-c856da94e339)</span>

---

Vlad Zamfir: Honestly not excited about plasma.io ... I stopped working on "baby chains" in early 2015 because sidechain state channels are not that good.

<span style="color:silver;font-size:11px">Source: [twitter.com](https://twitter.com/VladZamfir/status/895599682315014144)</span>