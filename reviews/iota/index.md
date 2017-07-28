## IOTA: a novel micro-transaction crypto-token optimized for the Internet-of-Things.

IOTA aims to become the backbone of [Economy-of-Things](http://www.nasdaq.com/article/what-is-the-economy-of-things-cm524736) and the world standard for micro-transactions. Its creators maintain they've achieved remarkable results in such important areas as: scalability, storage, bandwidth and fees (actually there are no fees, just like Steem). IOTA’s design diverged radically from other blockchain crypto-currencies. It's a blockchain but without blocks - it makes use of [Directed Acyclic Graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph).

---

**ECONOMY OF THINGS**

As the Internet-of-Things keep expanding, the need for interoperability and sharing of resources become a necessity. IOTA enables companies to explore new business-2-business models by making every technological resource a potential service to be traded on an open market in real time, with no fees.

**LEDGER OF THINGS**

In this new autonomous Machine Economy IOTA will be the backbone. The Tangle ledger is able to settle transactions with zero fees so devices can trade exact amounts of resources on-demand, as well as store data from sensors and dataloggers securely and verified on the ledger.

**THE TANGLE**

The main innovation behind IOTA is the Tangle, a revolutionary new blockless distributed ledger which is scalable, lightweight and for the first time ever makes it possible to transfer value without any fees. Contrary to today’s Blockchains, consensus is no-longer decoupled but instead an intrinsic part of the system, leading to decentralized and self-regulating peer-to-peer network.

**MICRO-TRANSACTIONS**

For the first time ever true micro and even nano-transactions are enabled due to the unique IOTA Tangle architecture, providing developers with a brand new set of tools for their applications in both IoT and Web. This nurtures brand new business opportunities for companies that prohibitive fees has kept in the realm of the impossible until now.

**DATA TRANSFER**

Core feature of IOTA is the ability to transfer data through the Tangle. IOTA gives you several options to do so, making it possible to establish secure and authenticated communication channels between devices. All data which is transferred through IOTA is fully authenticated and tamper-proof - making attacks impossible.

**VOTING**

Although IOTA is uniquely suited for the Internet-of-Things, the Tangle enables a variety of different use cases that involve secure data transmission, especially for eGovernance. An important part of this sector is e-Voting. The exploration into this field of use-cases has already begun by several companies and academics.

**MASKED MESSAGING**

As the first extensible module of the IOTA core, MAM enables nodes to exchange data through the Tangle, fully authenticated and encrypted. This means that your devices can transmit valuable and sensitive data with quantum-proof security through the Tangle, ready to be analyzed later. MAM makes it possible to share data with multiple parties easily, similar to a radio, multiple parties can simply tune in on your frequency and get the broadcast data.

**EVERYTHING AS A SERVICE**

While the whole world has adopted the ‘Sharing Economy’ in areas like driving and accomodation, IOTA enables a whole new realm where anything with a chip in it can be leased in real time. Most of our belongings stay idle for the vast majority of time that we possess ownership of it, but through IOTA a lot of these things like Appliances, Tools, Drones, eBikes etc. and resources such as computer storage, computational power, WiFi bandwidth etc. can be turned into leasing-services effortlessly.

**ANYTHING THAT NEEDS A SCALABLE LEDGER**

The distributed ledger revolution has only barely begun, the vast majority of use-cases has not even been thought of yet, and with the next generation ledger that IOTA created developers will be able to invent even more solutions.

<span style="color:silver;font-size:11px">Source: [iota.org](https://iota.org/)</span>

---

### Tangle-blockchain interoperability

IOTA does not seek to replace the blockchain entirely, it also acts as a supplementation to the current blockchain ecosystem by acting as a oracle for smart contract platforms like Ethereum and Rootstock. Additionally it increases security of blockchains by enabling the ability to include checkpoints for transactions.

### Tangle vs Blockchain

IOTA’s blockchain solves the following problems of its blockchain cousin:

**Centralization of control**

As history shows, small miners form big groups to reduce variation of the reward. This leads to concentration of power (computational and political) in hands of few pool operators and gives them ability to apply wide spectrum of policies (filtering, postponing) on certain transactions. Although there are no known cases where pool operators abused their power, there have been several instances where the opportunity were present. This possibility in a monetary system powering a multibillion (in USD) industry is completely unacceptable.

**“Obsolete” cryptography**

Although large scale quantum computers do not exist yet, future oriented companies have already begun initiating the steps towards quantum-resistant cryptography. From a security point of view it makes perfect sense to assume that hardware capable of cracking classical cryptoalgorithms may appear in the very near future, so preparation is the only defense.

**Inability to conduct micropayments**

Transaction fees are used to cover miner expenses and mitigate spam-attacks. They also set a threshold on the minimum amount of a payment below which money transfers become inexpedient. 

**Partition intolerance**

Blockchain-based currencies are unable to survive long-sustained partitioning of the network because this may lead to reversal of a large number of transactions. It is also impossible to initiate an intentional partitioning in cases when it is required.

**Discrimination of participants**

Existing cryptocurrencies are heterogeneous systems with clear separation of roles (transaction issuers, transaction approvers). Such systems create unavoidable discrimination of some of their elements which in turn creates conflicts and makes all elements spend resources on conflict resolution.

**Scalability limits**

Some cryptocurrencies have hard limits on the maximum transaction rate and this limits cannot be removed in a decentralized manner. A magic number of a limit set before the launch cannot satisfy requirements of a system unless it is set by a person with extraordinary prediction skill. A too low value may hinder growth of the userbase, a too high value may open system to different kinds of attacks.

**High requirements for hardware**

Bitcoin-derived cryptocurrencies use its original script-based approach which allows implementation of a wide range of use-cases. Other currencies use an approach similar to one used by banks but add extra features. They both substantially raise requirements for hardware because of complex transaction processing logic.

**Unlimited data growth**

Storing of all state transitions leads to fast growth of data while does not increase stored balance information significantly. This inefficiency cannot be removed even with data pruning technique and high popularity of the currency may lead to its collapse.

<span style="color:silver;font-size:11px">Source: [bitcointalk.org](https://bitcointalk.org/index.php?topic=1216479.0)</span>

---

Nearly all Blockchain implementations today have several problems, so lets summarize them real quick:

- **Scalability:** Because of a transaction limit, Bitcoin/Ethereum cannot handle a high load of transactions. This is one of the base requirements for IoT if it wants to utilize one backbone for handling tx's/messages.
- **Storage:** With Bitcoin at 60gb and Ethereum coming close to 10gb, the requirements for running a full node in order to interact with the network are simply **way** too high for IoT devices which don't have the luxury of having a spare 60gb available for storing a Blockchain.
- **Bandwidth:** In order to keep up with the network a device would have to download 1 Block (roughly 1mb) every 10minutes. Because IoT is synonymous with **resource constrained environment**, many IoT devices will have a difficulty keeping up with the network with limited internet access.
- **Fees:** Because of the way these Blockchains achieve consensus, tx fees need to be paid. This makes them pretty useless for microtransactions.

Now don't get me wrong, the above is the current state of Blockchains and there are some great proposals to improve Bitcoin/Ethereum beyond their current capabilities, but none of the current proposals make Bitcoin nor Ethereum a great choice as the backbone at the underlying IoT layer. This is where IOTA comes in place which is **lightweight** (both with the client, and with the Tangle itself due to snapshotting), **scalable** (~100tps on-tangle, near infinite off-tangle) and it has **no fees**.

Apart from monetary transactions (which can be nano-transactions), IOTA also allows you to send messages, which make it a perfect solution for IoT devices to communicate with each other and with the outside world. Now you may say "dude, TCP/IP can do that as well..", yes, but one of the core problems of machine-to-machine communication is the difficulty of proving the authenticity and integrity of a message. By doing messaging on a distributed ledger you can prove the authenticity and integrity of a message and you also make it tamper-proof.

Now for IoT I see a great synergy between Ethereum and IOTA. Ethereum could run in a kind of central controlling station while IOTA runs on all the tiny devices and connects them between each other and the Ethereum blockchain. That is exactly the kind of direction we are going towards, because we want maximum interoperability with other Blockchains to create an environment where IOTA is the backbone of the Internet of Things, and other aspects of an application are handled by different Blockchains (mostly smart contracts).

<span style="color:silver;font-size:11px">Source: [forum.iota.org](https://forum.iota.org/t/eli5-iota-vs-slock-it/229/2)</span>

---

IOTA is not a direct competitor to Ethereum. IOTA is similar to Lightning Network or Raiden, these protocols allow for great scalability and micro-transactions.

**Advantages of the IOTA network**:

- No fee transactions, which makes micropayment possible
- Removes miners, everybody contributes to the network
- Unlimited transaction rate, each person that sends a transaction is supposed to process a transaction, which theoretically means unlimited scalability.
- Un-forkable, the network can’t split into new separate networks like ETH and ETC.

**Disadvantages of the IOTA network**:

- Can’t do smart contracts

- The promise of free transactions is highly theoretical and node pools with heavy weights in the DAG could force transactions through themselves and charge fees. This issue has yet to be addressed by the development team.

- An attacker doesn't have to outpower the entire honest computational power of the network, but just the honest computational power of the network actively making transactions at any given time


<span style="color:silver;font-size:11px">Source: [steemit.com](https://steemit.com/iota/@wolfofcrypto/iota-is-it-worth-one-iota)</span>

---

It hasn't scaled yet. An Ethereum transaction is faster by an order of magnitude. IOTA is a slow as frozen molasses right now.

IOTA is dead in the water right now without the central light balanced server nodes that have been set up. That will obviously be fixed with more users and in more time.

<span style="color:silver;font-size:11px">Source: [reddit.com](https://www.reddit.com/r/Iota/comments/6i0c0m/do_you_think_iota_could_become_the_1/)</span>

---

Why is IOTA slow? Confirmation times depend on 3 main things:

1) Number of transactions on the Tangle (the more transactions, the more opportunity for your transaction to be verified by others doing PoW)

2) Tangle topology - right now the network is clustered because of how full nodes are connected. Topology is in a constant state of flux, and will naturally be smoothed out as the number of nodes increases.

3) Your location in the Tangle. If you're located in one cluster, and you're trying to send to a node in a different cluster, it may take a very very long time for that transaction to confirm. If you're sending within your cluster, it can take a few seconds

<span style="color:silver;font-size:11px">Source: [reddit.com](https://www.reddit.com/r/Iota/comments/6lr11x/super_slow_confirmation_timesor_is_it_just_me/)</span>

---

For now, a nice number of legit companies and institutions that collaborate with IOTA have been *officially* announced:

- Microsoft
- Innogy
- Ubuntu Canonical
- University of Lancaster
- Hyperledger
- Chain of Things
- Countless Companies behind NDA’s
- Countless Academic collaborations
- To the foundation members and advisors connected companies

We know that there are a lot more judging by the slack inhabitants that are not announced yet.

<span style="color:silver;font-size:11px">Source: [tangleblog.com](http://www.tangleblog.com/2017/05/10/iota-a-summary-of-success/)</span>

---

[NaughtyCoinGeek](https://www.reddit.com/user/NaughtyCoinGeek): My main concerns:

- "No fee" is not true. even with its supposed scalability there has to be protection from spamming. So you have to do a little PoW to generate a transaction. There's your fee. So it's not really "no fee". But there is supposedly a very large supply of transaction space so fees should stay low.
- Not mineable: the brilliance of PoW mineable coins is that any tech that can attack private keys will do better to mine. So attacks get honeypotted to mining. My sense here is that without any mining reward for PoW, there will be computational attack vectors that can only be counteracted by centralizing.
- It's not "better enough". To overcome the network effect of incumbents it's not enough to be better, you have to be 10x better. I don't see it being 10x better.
- Centralized: Currently there is a central "milestoner" that protects against spam attacks. I haven't heard what is the way forward to transition away from that.
- Protocol upgrades. With a tangle instead of a blockchain, what is the analogue of a hard fork upgrade? How do you get a decentralized tangle protocol that can also be upgraded?

[SirTuffers](https://www.reddit.com/user/SirTuffers): I was under the impression there was no fee because *you're* doing the work instead of the miners (to whom the fee normally goes). In IOTA, if you want to send 1 transaction, you have to confirm 2 others. Surely this means that spammers are discouraged, as they would have to do a lot of work *themselves* if they want to spam?

They have also specifically said themselves that it is protected from spam. They have already done a 300% load DDoS attack on the system and it held fine. Doesn't prove it's *invincible*, but I don't think it's as big a concern as some make it out to be.

[Steel_Neuron](https://www.reddit.com/user/Steel_Neuron): I'm doubly skeptic of any blockchain technology that attempts to target IOT and general purpose embedded devices, as a professional embedded developer I'm aware of how old school and slow moving the industry is, which would put another 3-5 years before a technology like this is adopted in that space.

<span style="color:silver;font-size:11px">Source: [reddit.com](https://www.reddit.com/r/CryptoMarkets/comments/6ity1k/iota_any_opinions/)</span>

---

# THE TECH BEHIND IOTA EXPLAINED

### Scalability

1.) If you want to use IOTA, and to send a transaction, you need to confirm two transactions before you may send yours. This simple rule leads to: **the more people use IOTA, the more transactions get referenced and confirmed: confirmation rates and timings are getting better, the more people use it, unlike Blockchains. **

2.) Compared to traditional blockchains of the 1st and 2nd generation, IOTA has no blocks and therefore no scalability issues the more transactions are conducted and addresses are generated. How so, you may ask?
What specific advantage does IOTA get in terms of scalability, when there are no blocks at all?
IOTA doesn’t need to order values of seeds and addresses in the right order. This “trick” it uses is, that all transactions can be saved on different devices, at different places, unordered, even split. So when you are synching your node, it just iterates through all transactions. The values from all transactions will be grouped into their addresses, even if they are in their previous order or not.

When the Tangle processed all transactions, the addresses (aka ledger) will contain all balances. It only needs to verify that none of the addresses contain negative balances.

This feature gives lots of benefits. For example, MapReduce, a programming model, can be used with this feature, to process large datasets parallel on many devices, also constrained devices. Perfect for a distributed ledger, where countless devices are bound together.
Furthermore: The tangle caches address-balances of a subtangle, to combine them with newly discovered transactions.

A second trick IOTA uses is the appliance of multi transactions. They are made of a diverse number of chained transactions while using the same address.
In addition, these chains are set up that only the first transaction has value, while all following transactions have a zero-value. That means that on top of the fact that there is no necessity of order, there is no necessity of skipping transactions.

In conclusion:  Transactions with IOTA can be processed very fast, unordered (Commutative Law / Linearity (a+b = b+a) ) and unfiltered because zero-values are added behind non-zero-value transactions. There is no max-count of transactions in one block like in blockchains and there will certainly be no blocksize-debate.

*Eli5: It makes no sense to sort a puzzle just from one corner,  piece after piece if you can have multiple eyes looking simultaneously and randomly for the right pieces to form the puzzle, from multiple corners. The more eyes, the faster it gets.*

Background: [MapReduce](https://en.wikipedia.org/wiki/MapReduce)

3.) People argue that IOTA has a problem in the future, in hindsight of the growing size of the Tangle. What is happening now to prevent that is:
a) people have to use PoW, they can’t just spam the tangle without having to pay for it with time and electricity.
b) snapshotting reduces the size of the tangle frequently. For now, manually in coordination with the core devs, later automated and locally.

Keep in mind, that the bottleneck for the speed and usability of IOTA in the future is not confirmation rate or size of the tangle (because storage is getting better and is really cheap already), but bandwidth.
Without a solid infrastructure, the Tangle can be limited in its functionality.

###  Approval Of Transaction Now And In Post-Coordinator Times

After some dense conversations, I can tell you that the intrinsic approval of transactions is no piece of cake. Therefore I decided to also “explain like I’m five” at least for the latter part.

We basically have two phases of approval.
Now and in times after the coordinator is arranging transactions. As already mentioned, this will ultimately be the case in July 2017, but maybe earlier depending on manual claims by IOTA owners, testing and size of the tangle.

Now the proof of work is done with a Hashcash-similar algorithm, which is also used with Bitcoin. Hashcash is basically an assignment for your node to work and to calculate a missing piece of a puzzle so to speak.

The coordinator is deciding, where the tangle needs to grow and where to coordinate the next steps. The coordinator also marks transactions which are already confirmed. That’s the reason IOTA is not distributed yet per [definition](https://cdn-images-1.medium.com/max/600/1*nnpzTe1hx74WKICL3Gj34A.jpeg), but decentralized.

In practice, IOTA is decentralized and could run completely free, without the coordinator, but for now, this system is set up as a protection mechanism against 34% attacks, while the tangle ledger isn’t fully matured and big enough to catch such attacks.

Interesting read: [The Transparency Compendium](https://blog.iota.org/the-transparency-compendium-26aa5bb8e260?gi=4f0a3f696b4e)

Approval of transactions in post-coordinator time works with Random Walk Monte Carlo-Methods. That’s a random integral algorithm to jump to random transactions and approve them (to put it simple).                                                                                                            

The Random Walk Monte Carlo-Method will be enabled once the coordinator is shut down. Then, the IOTA Reference Implementation ( IRI) will be upgraded to the IOTA production Implementation to support the IoT in industrial appliances. An additional step is the usage of the ternary JINN processors.

So all in all, the approving-time depends on the network topology and a number of transactions per second. When the coordinator is shut down, the *freed* tangle will be operative.

That being said, there is no theoretical scalability-limit and therefore an incredibly fast network.

Further information on [Hashcash](https://21.co/learn/proof-of-work-using-hashcash/#what-youll-learn)

###  Subtangle

I’d like to pin down this lovely stolen “explain like I’m 5-story” about Alice and Bob about spending IOTA within a subtangle or out-of-order tangle to clear things up.

> *Imagine that Alice sends 10 iotas to Bob, she attaches her transaction to the tangle and in 5 mins Bob spends 7 iotas from these 10. Unfortunately, Alice’s transaction might be attached to some part of tangle that is not widely seen, but Bob’s transaction is picked by 99% of the network right away. It would be a bad idea to make Bob wait just because he had business with a woman from “suburbs”. IOTA allows to include Bob’s transaction and during some period of time the ledger will be inconsistent (because the majority thinks that Bob spent iotas out of thin air), but no one really verifies that the ledger is consistent every single second. 2 mins later Alice’s tx might be adopted by the network and then everything will be fine.*
>
> *Even more, we can imagine a situation when Alice doesn’t have iotas and promises Bob to pay later, Charlie trusts Bob and can accept his transfer. Later (in a few weeks), when Alice finds iotas and sends them to Bob’s address not only Charlie but the rest of the network accepts that subtangle as part of the global Tangle.*

Important: For now, the tangle is not scalable nor allowing out-of-order tangles because the milestone-coordinator is organizing transactions in order to establish the tangle.

Background: [http://www.tangleblog.com/what-is-iota-what-is-the-tangle/](http://www.tangleblog.com/what-is-iota-what-is-the-tangle/)

###  JINN-Processors

Not many information about the ternary JINN processors is public supposedly due to contracts.

A few things, however, are known, for instance, that these chips are the first of their kind and able to disrupt and change big branches of the IoT.

JINN are “general-purpose-processors” with the purpose to conduct thousands of transactions per second.

That is possible because unlike binary processors, they can go into more states:+, – and circulating around zero, so 3 states all in all. These 3 states perform transaction very balanced, which is quite helpful to build a self-organizing and self-sustaining network like the tangle.

A good read about the theoretical advantages of a ternary computer you can find here:

[The balanced ternary machines of Soviet Russia](https://dev.to/buntine/the-balanced-ternary-machines-of-soviet-russia)

Founder [David Sønstebø](https://blog.iota.org/@DavidSonstebo?source=placement_card_footer_grid---------0-45) on JINN: “*JINN is a custom made Polymorphic Processing Unit which utilizes asynchronous circuits and trinary logic gates, a component of this is the ‘Curl Hasher’ (essentially a tiny ASIC), this ‘Curl Hasher’ component will be made open source so that any chip manufacturer can add it to their chips trivially. We’re talking a completely negligible amount of logic gates here, so zero extra cost, size trade off or implementation issues*”

###  Cryptography and Quantum Resistance

Quantum computing will be the end of encryption as we know it. Against the background of the global interconnectedness of the IoT, a problem that demands a secure solution.

IOTA has an integrated quantum-resistant algorithm, the Winternitz One-Time Signature Scheme.

The Winternitz hash is known as a post-quantum signature because quantum attacks don’t significantly lower the security given by this hashes.

Dr. Sergui Popov compares IOTA with Bitcoin to explain quantum resistance:

> *As of today, in average one must check around 268 nonces to find a suitable hash that allows to generate a block. It is known (see e.g. [13]) that a quantum computer would need Θ(√ N) operations to solve a problem of the above sort that needs Θ(N) operations on a classical computer. Therefore, a quantum computer would be around √ 2 68 = 234 ≈ 17 billion times more efficient in Bitcoin mining than a classical one. Also, it is worth noting that if blockchain does not increase its difficulty in response to increased hashing power, that would lead to increased rate of orphaned blocks. Observe that, for the same reason, the “large weight” attack described above would also be much more efficient on a quantum computer. However, capping the weight from above (as suggested in Section 4) would effectively fence off a quantum computer attack as well, due to the following reason. In iota, the number of nonces that one needs to check in order to find a suitable hash for issuing a transaction is not so huge, it is only around 38 . The gain of efficiency for an “ideal” quantum computer would be therefore of order 34 = 81, which is already quite acceptable (also, remember that Θ(√ N) could easily mean 10√ N or so). Also, the algorithm is such that the time to find a nonce is not much larger than the time needed for other tasks necessary to issue a transaction, and the latter part is much more resistant against quantum computing. Therefore, the above discussion suggests that the tangle provides a much better protection against an adversary with a quantum computer compared to the (Bitcoin) blockchain.*
>
>  

Background: [Winternitz OTSS](https://eprint.iacr.org/2011/191.pdf)

### Concerning a possible attack-vector, that has been discussed lately

First, you should have a look at [The Transparency Compendium ](https://blog.iota.org/the-transparency-compendium-26aa5bb8e260?gi=4f0a3f696b4e)

Then, take a look at [The Tangle is safe, a Commentary](http://www.tangleblog.com/2017/06/15/the-tangle-is-safe-a-commentary/)

And for those, that are still unsatisfied, let me end with this:

If you’re interested in discussing possible attack vectors, the IOTA Foundation is happy to discuss it and to provide you with funds to test those scenarios in order to develop a solution. For now, no attack vector has been proven successful.

<span style="color:silver;font-size:11px">Source: [tangleblog.com](http://www.tangleblog.com/2017/01/25/the-tech-behind-iota-explained/)</span>

---

*Please explain how can IoT devices be expected to do PoW?*

The *network* can be supported with spammers which help transactions to approve. These network spammers are either using CPU or GPU. The latter are much faster and able to conduct lots of tx per second. When IOTA is beeing used in a global network and for industrial processes, JINN ternary processors are used to conduct ten-thousand tx/seconds. Since we have a great scalability, there is no speed limitation so that most transactions in the future are conducted in seconds. 

*How can a device like this be part of the IOTA network because of the PoW requirement?*

Small devices just need to receive and broadcast a tx, the network spammers such as JINN or GPU-spammer will do their PoW for them. The computational power is therefore outsourced from small and smallest devices.

*How do IoT devices connect to the network since there is no automatic peer discovery? Does a manufacturer/user of these IoT devices have to manually configure every device with specific neighbours?*

a) Peer discovery was shut off because the network topology was suffering. For now, people in the tangle can either look for neighbors manually in our slackchannel under #nodesharing to run a full wallet or they can use the integrated light wallet, which is only connected to one node. A list of supplied nodes is here: [http://iotasupport.com/lightwallet.shtml](http://iotasupport.com/lightwallet.shtml)

b) Manufacturer most likely won’t need to look for single nodes for each and every device. Remember: the Jinn will be able to conduct thousands of tx a second so the solution will be somehow managed with that. I guess subtangles are part of the solution. But for this particular question, it would be your best option to ask one of our developers in our slackchannel. You can ask me (@limo) for help in slack. The invitation link for slack is under LINKS.

*That means the current software is not yet ready for this? – because currently, to send iotas require PoW, even when using light wallet.*

That tangle will be connected to a central server in your house, from there all sensors are connected to this server. So I guess companies who want to provide this kind of service have to create this special clientside-software for sensors on their own so that the sensors can be part of a subtangle or so. But I’m just guessing here.

Right now the tangle and the software directly connected to it is beeing developed and tested. Services on top of that, like an e-car-wallet, or smart data applications need to be developed by the companies who collaborate with the IOTA foundation or companies who have the capabilities to deal with the code and its API etc.

The user-software is fully functioning, by the way, so people can send and receive iotas, they can also try to build proof of concepts with it. IOTA has a javascript, python and C library, furthermore a working sandbox-environment. Needless to say, that core is improving the code and implementing new features all the time.

<span style="color:silver;font-size:11px">Source: [tangleblog.com](http://www.tangleblog.com/2017/01/03/byteball-vs-iota-token/)</span>

---

### IOTA creates new possibilities that were previously impossible

#### Machine economy

* Micro payments
  * House equipment rental
    * Air BnB (washer, dryer, locks)
  * Devices can buy goods themselves
    * Smartfridge
  * Gastronomy
    * Coffee shop / Coca-Cola-Automat
  * Gas / water / electricity
    * Digital meters / water / gas clocks
  * Pay on demand / stream on demand
    * Streaming services / music contracts
  * Electric charging
    * Payment model from Innogy
    * Customers may select cheap rates automatically
* Machines are customers and sellers
  * Industry processes are automated.
    * As part of the 4th Industrial Revolution
    * Technizations and innovations are difficult to stop
  * Machines take over jobs from people
    * Disruption everywhere.
  * Machines are taxed
    * For example, For each work step, for each product
  * Taxes can be used for other things
  * Universal Basic Income?
  * Social changes
  * Advanced future markets and a better system as a goal of transformation where everyone benefits.

#### Sensory Data Markets / BigData

* Statistics are valuable
  * Data sales
* Advertising
  * Create profiles, sell data. (Glass customers, controversial)
* Environmental data
  * Weather stations, climate change, vulnerability data
  * Free data for everyone, free of barriers, valuable for research
* Security related Data
  * Interpol, etc.

#### User Statistics (also BigData)

* Web pages
* Infrastructure adaptations
* Demography analysis
* Market analysis
* Location analysis
* Financing is calculated by means of experience

#### Decentralized Data-storage

* Decentralized hard drives
* Never again data loss
* No changes to the data are possible

#### Sharing economy

* Photovoltaics
* Equipment in the neighborhood
* Air BnB
* Car sharing
* Unlimited sharing possible, higher standard of living for all
* Consumption can be normalized / Disposable society

#### Data Integrity

* Everything is tamper-proof, because of a decentralized, synchronized network, which ensures the actuality of the data.

#### Notary / legal applications

* Why signatures if you have counterfeit-proof, unique transactions and hash values that are set up with time stamps irrevocably. (Also smart-contracts)

#### Democracy

* If a transaction is a voice, then a choice without election fraud can be ensured.
* On all levels
* Sensitive information can be sent and accepted fraudulently. (Fake news?)
* credibility
* emancipation

<span style="color:silver;font-size:11px">Source: [Google Docs](https://docs.google.com/viewerng/viewer?url=https://powr.s3.amazonaws.com/app_images/resizable/9898ed58-86f2-4b49-a503-db8a26f1106a/use-cases%2Benglish.pdf)</span>

---

[Time Has Come For Blockchainless Technology: IOTA’s David Sønstebø](https://cointelegraph.com/news/time-has-come-for-blockchainless-technology-iotas-david-s%C3%B8nsteb%C3%B8)

[The Blockchain-less Token IOTA is Ready to Take on the World](https://cointelegraph.com/news/iota-beta-internet-of-things)