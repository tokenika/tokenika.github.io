# Dan Larimer's response to Vitalik's remarks about DPOS voting and EOS fees

**In [his remarks](https://np.reddit.com/r/ethereum/comments/6qm0y2/is_the_ethereum_team_defending_their_ground/dkyk94c/) Vitalik brings up the issue of DPOS voting (low voter participation, tragedy-of-the-commons vulnerabilities, misalignment between coin holder interests with user interests), and the consequences of lack of fees in EOS (e.g. how to handle unexpected spikes in demand).**

>  The following text is an abbreviated (and slightly edited) version of Dan Larimer's article.

#### Client-side validation

DPOS block producers have no power to produce invalid blocks and every exchange will run a full node (or at the very least a partial node) and therefore directly validate the relevant subset of transactions.

Ethereum light-clients have to trust the block producers calculated things properly because they only check the hashes not the logic. Thus the failure condition is collusion of mining pools which is similar to collusion of elected block producers. The critical difference being that there are more elected block producers and their power is far more evenly distributed than the concentration of mining pool power.

#### Voting

Low voter participation has been addressed over the past 3 years through a combination of voting proxies, easier user interfaces, and a reduction on the number of things people have to vote for. All told participation has increased above 20% of total tokens. In case of Steem, concerns over "exchanges voting" were largely remedied via Steem Power (exchanges need liquid tokens), whereas in EOS it could be completely remedied via the constitution.

Furthermore, non-voters do not make things less secure. They keep tokens off the market which still makes it more expensive for an attacker to acquire stake. Large stakeholders have a huge incentive to vote to protect their wealth and an attacker would have to acquire more stake than the largest whales in the system. Given the turnout on Steem and BitShares and a market cap like Ethereum this would cost an attacker billions of dollars (assuming their buy pressure didn't increase price) and they could easily be forked out if it became a problem.

If attacker is a collusion by the largest whales, then either the whales think the "attack" is a feature that will enhance the protocol or the "community" will fork the whales out. Bitcoin and Ethereum have both seen what happens when those with large influence use it to change the rules against the minority interests (Ethereum Classic and Bitcoin Cash).

#### Fees

Try to implement Steem on Ethereum and you would drive all the users away due to fees alone.

Due to the fractional reserve nature of the blockchain bandwidth allocation, most people only need to purchase enough for their "base load" and the network can handle the surges in demand. Only in situations where the network is 100% congested will you need to purchase enough to cover the 99th percentile usage; however, if people are buying enough to cover the 99th percentile usage then the network will never be 100% congested because they will be holding unused bandwidth during the average usage. Therefore, we can conclude that the market will automatically balance things out and people will not have to buy based on peek usage but average usage.

#### DPOS block producers not being punished for misbehaving

If you ignore the loss of future revenue and reputation, DPOS can offer trivial slashing for producing two blocks with the same timestamp and thus attempting to create a fork. It is also trivial to add a bond on producers that stake holders can vote to confiscate for a wide range of objective and subjective violations of the constitution.

<span style="color:silver;font-size:11px">Source: [steemit.com](https://steemit.com/eos/@dan/reponse-to-vitalik-s-written-remarks) by Dan Larimer, Aug 2017</span>