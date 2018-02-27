# How does IPFS compare with the SAFE Network?

Dan K on March 2017

---

The big difference is in the scope of each project.

IPFS is only focusing on a proof of concept of a distributed storage, as it name implies, it is just a file system, and that is about it.

MaidSafe is actually redesigning the Internet as a whole, becoming both a data and a communications network with the following properties that are integral to its engineering; extremely robust anonymity, security, censorship resistance, self-authentication, self-encryption, economic incentives (with its cryptocurrency), and very importantly: autonomous.

With MaidSafe’s SafeNetwork, you can host both static and dynamic websites. But storage is only half the story. You can chat, have videoconference, streaming and reach broadband speeds (Imagine broadband speeds, but with anonymity stronger than TOR)

Further down the pipeline they are also planning to incorporate distributed computing to it.If you compare both projects IPFS is a stripped down version of MaidSafe. IPFS is NOT anonymous, in fact it broadcasts your internal network’s topology to the whole world.

The main difference is that EVERYTHING is encrypted and stored by default in maidSAFE.

IPFS only stores duplicate copies of your data when somebody chooses to keep copies of your data. I think the main reason is that there is a lot of unsavory data out there that a lot of people wouldn't want to store on their machines. IPFS solves this by making storage optional, MaidSAFE solves this by breaking all files into 3 pieces (minimum) encrypting them with each other's hashes then storing them in the DHT encrypted and anonymously. So the nodes have no data of meaning... and each chunk is backed up into 4 nodes and the network manages that there is always 4 copies of each chunk online.

So the data only has meaning when it is re-assembled by the owners with his key.If one node goes offline, the data managers immediately find another node to store the 4th copy. 

And they periodically verify that the stored chunks are valid and not corrupted by appending a random number to the encrypted chunk and then rehashing it. If all chunks including the 4 back ups coincide with the same hashes, they rewarded with Safecoins (this is the proof of storage, that is how the farming works), the ones that don’t return the same result are automatically ranked lower.

Security is a big concern with IPFS. If I ask for a hash of a file, my neighbor node upline will know that the file exists. If I don't want him to see the data inside it must be encrypted - but that is an outside process (With SAFE it is a built in process by default)

Also the most salient difference is MaidSafe’s cryptocurrency SafeCoin which leverages from the design of its distributed network, and because it is the only one that it is NOT blockchain based it has an unique advantage: It is anonymous, instantaneous (infinitely scalable) and FREE (absolutely no transaction fees!) by default. These properties would make it the most likely candidate of becoming the digital cash of the future.

Also the issuance of the currency is fully distributed with negligible energy consumption, even smartphones are expected to be able to participate from its ‘farming’, and centralization is discouraged as it penalizes any resource that deviates 20% from the global average.

With the introduction of the cryptocurrencies to MaidSafe’s SafeNetwork it also turns the monetization model of the web upside down. Ad Networks wouldn’t be needed anymore to make money off your websites (and off your users). The network itself (autonomously) can reward you for sharing resources, and for creating popular content, as part of the minting and coin recycling process, besides the payment or tips you would receive from other users.

For censorship resistance, the SafeNetwork uses all ports and all available transport protocols and NAT hole punching until it finds a connection towards the network. Also, because all connections are encrypted even before it leaves the computer (self-encryption) there isn’t even a cryptographic hand-shake to be fingerprinted by firewalls.

SafeNetwork’s anonymity is achieved because after the first bootstrapped node, it drops the IP protocol and uses only XOR distances for routing. Each client gets assigned randomly a new ID. For more information about this, refer to [this YouTube video](https://youtu.be/w9UObz8o8lY).

Because MaidSafe can do whatever IPFS can do and way much more, I think that when the beta version is released in the next couple of months, IPFS will become quite redundant very fast.

IPFS’s big advantage is that because of its limited scope, it works now and you can play with it. SAFE is still weeks, or perhaps months from being released.

MaidSafe team made a huge ambitious gamble trying to eat the whole elephant at once, and considering the rate of the recent developments, I think it will pay off very big.

So my opinion about dApps is very clear: the SafeNetwork (if it succeeds in accomplishing its goals) it’s the most likely candidate to win the mass adoption in all areas: storage, hosting, anonymous and secure network, dApps and cryptocurrency adoption.Recommended reading if you are interesting in learning more details:
[Safe Network explained using bitcoin terminology](https://safe-network-explained.github.io/safe-for-bitcoiners)

And you are welcome to participate in the SafeNetwork forum: [SAFE Network Forum](https://safenetforum.org/)

---

Source: [quora.com](https://www.quora.com/How-does-IPFS-compare-with-the-SAFE-Network)