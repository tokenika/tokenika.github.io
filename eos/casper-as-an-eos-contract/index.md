# Casper as an EOS Contract

**DPOS, EOS consesnus mechanism, could easily be tweaked to emulate Casper, Ethereum's consensus mechanism. Whereas the opposite is not true: Casper is not able emulate DPOS. However, according to Dan Larimer, this is would not be beneficial, as DPOS, despite its limitations, is the ultimate solution in the blockchain space.**

>  The following text is an abbreviated (and slightly edited) version of Dan Larimer's article.

#### Two parts of the problem

There are two parts to the Casper protocol, the proposal mechanism and the consensus mechanism. The proposal mechanism produces a sequence of blocks that link together and the consensus mechanism creates a checkpoint every 100 blocks.

Under the hybrid proof-of-work model Ethereum will use POW blocks as the proposal mechanism and the Casper algorithm to reach consensus on checkpoints.

#### What's the main idea of Capser's consensus mechanism?

Casper is first and foremost a protocol based on mathematics and game theory. This protocol attempts to reward those who agree while punishing those who disagree. It also has properties that punish all participants if certain objective measures of mischief are observed.

#### The importance of the proposal mechanism

The proposal mechanism determines what transactions get included in blocks and what transactions are censored. It also determines the set of blocks available to the consensus mechanism. 

Thus the proposal process is what determines centralization of production and censorship. Shutting down the proposal process shuts down the network as the Casper consensus process depends upon a valid source of produced blocks. All Casper provides is a economic measure of finality every 30 minutes.

We can conclude from this that the vast majority of the real consensus problems fall within the responsibility of the proposal mechanism. We can also see that Casper does nothing to improve the performance. Lastly, by the time an Ethereum block is buried under 30 minutes of POW the probability of reversal is so small that the relative cost of "casper insurance" likely far outweighs the actual risks involved.

#### Casper as an EOS Application

Given that Casper's proposal mechanism is abstract, it is trivial to replace it with DPOS. In other words, where Ethereum uses POW we can use DPOS.

Or we could look at it from other perspective: DPOS currently uses the longest-chain rule to sort out potential forks. However, the EOS community could elect to adopt Casper as a contract to increase the perceived security of their blockchain. Given the almost complete lack of forks in DPOS this hardly seems necessary, yet it still could be done.

#### DPOS is pipelined Casper

There are two independent parts of the DPOS algorithm: selecting the producers and reaching consensus. If you make the producer selection based upon size of the producer bond then you replace voting for producers with producer bonds. If you reinterpret the DPOS block production schedule as a pipelined sequence of Casper epochs then you can apply the Casper slashing conditions while having all the speed and benefits of DPOS.

#### Governance

What Casper does not solve is the governance problem. Layered on POW governance would be left to block signaling, or layered on proof of stake, it would amount to stake weighted direct democracy among validators. Whereas under DPOS governance is multi layered delegation to a panel of equally weighted producers.

#### Harsh code-is-law game

Casper creates a game where honest mistakes caused by software bugs, network disruptions, or griefing peers may cause unexpected and undeserved losses. This risk may be difficult to access and may discourage participation of honest players. The slashing conditions are a harsh code-is-law kind of governance that leaves little room for honest mistakes that caused no measurable harm.

#### Conclusion

It is still not clear that Casper will result in more relevant security or decentralization than we have with POW and traditional POS. I remain convinced that DPOS provides the best possible proposal algorithm for the Casper consensus algorithm, but I am unconvinced that Casper adds any meaningful value. After all, a properly functioning bug-free version of DPOS produces no forks and achieves irreversible checkpoints 30 times faster.

<span style="color:silver;font-size:11px">Source: [steemit.com](https://steemit.com/eos/@dan/casper-as-an-eos-contract) by Dan Larimer, Aug 2017</span>