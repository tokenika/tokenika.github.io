# Dan Larimer's reponse to Vitalik's remarks on EOS

**In [his remarks](https://youtu.be/SuY6L1nhWxM?t=495) Vitalik claims that EOS can process more transactions due to the fact that Ethereum has more features than EOS (and gives the lack of merkle trees as an example). Then he claims that in EOS there is no way to verify for yourself that everything is happening correctly, unless you run a resource-intensive full node. And finally, he claims that EOS scalability comes at the cost of reduced decentralization and thus increased vulnerability for the blockchain to be shut down by a government.**

>  The following text is an abbreviated (and slightly edited) version of Dan Larimer's article.

#### Merkle trees in EOS

EOS does have a merkle tree over all the transactions within a block. This means it is possible to prove you have been paid without having to process all blocks nor trust the full nodes. In fact, these proofs are smaller than ETH because light nodes don’t even require the full history of block headers.

#### Blockchain state as a Schrödiger’s cat

We can make the analogy that Blockchain state is like [Schrödiger’s cat](https://en.wikipedia.org/wiki/Schr%C3%B6dinger%27s_cat): you can never actually observe it or prove anything about it except by opening the box to find out if the cat is dead or alive. More specifically, while you can prove what the state was 1 minute ago (when you last opened the box), you cannot prove what the state is right now. At any time a transaction could mutate that state and it will no longer be the same as when you read it. The only exception is the use of “time locks” that assert the state cannot be modified for some time. Heavy use of time locks will crush performance and is of limited application.

#### Different approach for blockchian state validation

In Ethereum you have to trust the light clients are validating proofs and syncing from the proper blockchain. The merkle proofs you do generate about state are quickly dated and irrelevant.

Whereas in EOS:

* Nodes are allowed to validate partial state. This means that not all nodes need to run every contract. This in turn means it is possible to know the state of the applications and contracts you care about without having a highly resource demanding full node.

* Light clients can prove what actions users took (transactions), therefore, they can prove payment. 

* If a proof is really necessary they can broadcast a transaction that will assert the state they care about.

* Finally, everyone in the EOS ecosystem is contractually bound by a constitution and if the API nodes lie about blockchain state there will be cryptographic evidence of their lie and they can be held accountable for damages.

#### The trade-off between scalability and centralization

Vitalik claims that achieving scalability by having larger nodes makes the system more centralized. This of course demands a comparison, “more centralized than what”.

Let's take a look at the distribution of block producing nodes on Ethereum: two pools control 51% of the hash power and can trivially ignore blocks produced by all the other pools.

The fact of the matter is that when it comes to block producers, Ethereum and every other protocol is far more centralized than the DPOS blockchains; especially when you use [meaningful definitions of centralization](http://bytemaster.github.io/article/2015/01/13/Decentralization-of-Nxt-vs-BitShares/) (such as number of unique producers per transaction confirmation window).

#### The risk of being shut down by governments

Vitalik’s final point is that DPOS can be shut down far more easily by governments, ISPs, and corporations. The fact of the matter is that Ethereum and Bitcoin have already suffered denial of service attacks, whereas Steem and BitShares have not, despite attempts to flood the network. It would be trivial to cripple Ethereum’s network by taking out 90% of the hash power with 7 nodes.

The elephant in the room is that all of these public blockchains rely upon a peer-to-peer discovery process. Governments and ISPs around the world know exactly where every Ethereum node is and can trivially shutdown any and all public endpoints.

In EOS, block producers and API endpoints can be setup in the most free jurisdictions.

#### Conclusion

EOS is designed around far more realistic assumptions and logic and achieves scalability by avoiding the dogmatic fallacies promoted by Bitcoin and Ethereum maximalists. DPOS is more decentralized in practice by any real measure of decentralization. Vitalik’s claims of government resistance ignore fundamental properties and vulnerabilities of any public blockchain.

<span style="color:silver;font-size:11px">Source: [steemit.com](https://steemit.com/eos/@dan/response-to-vitalik-buterin-on-eos) by Dan Larimer, Aug 2017</span>