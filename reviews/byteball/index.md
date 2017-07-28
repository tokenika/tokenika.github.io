## Byteball: Just like Iota, it uses tangles but with the difference that Iota is specialized for machine-to-machine use, while Byteball is specialized for human-to-human applications. They seem much complementary.

Unbounded scalability, fast confirmations, no miners, no blocks, low fees.

Byteball data is stored and ordered using [directed acyclic graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph) (DAG) rather than blockchain. This allows all users to secure each other's data by referencing earlier data units created by other users, and also removes scalability limits common for blockchains, such as blocksize issue.

Blockless design is simpler because there are no blocks, there are only transactions. Users just add their transactions to the end of the DAG themselves, they don't have to wait when miners create a new block and there is no guesswork whether miners will include your transaction in the block.

The consensus algorithm used to protect from double-spends is based on establishing a total order within the DAG. This is achieved by selecting a chain, called main chain, which gravitates towards units issued by commonly recognized reputable users — witnesses. See the [white paper](https://byteball.org/Byteball.pdf) for details.

## Core features

* #### Atomic exchange

  When two parties sign a single unit that executes both legs of the exchange, the two transactions either happen simultaneously or don't happen at all. It is no longer necessary to trust any centralized exchanges.


* #### Regulated assets

  Regulated institutions can issue assets that are compatible with KYC/AML requirements. Every transfer of such asset is to be cosigned by the issuer, and if there is anything that contradicts the regulations, the issuer won't cosign.

* #### Multi signature

  For security, you can require that your funds be spendable only when several signatures are provided, e.g. from your laptop and from your phone. For shared control of funds, signatures from different people may be required.

* #### On-chain oracles

  When dealing with untrusted counterparties, you can lock the funds on an address that is spendable either by you or by the counterparty, depending on the events registered to the database by trusted data providers — oracles.

* #### Immutable storage

  Once stored in the Byteball database, the data can neither be revised nor removed.

* #### Settlement finality

  After certain criteria are met, a new transaction becomes final. It cannot be revised even by a powerful attacker. No guesswork about the right number of confirmations, no 51% attacks.

<span style="color:silver;font-size:11px">Source: [byteball.org](https://byteball.org/)</span>

---

### What Is Byteball?

Byteball is a decentralized system where you can store unique types of data – including everything from currencies to property titles to debt. The system, like other [blockchain technology](https://bitcoinexchangeguide.com/blockchain-distributed-ledger-technology/), allows you to store data in a tamper-proof way.

Byteball storage units are linked to one another. Each storage unit includes one or more hashes of earlier storage units. This confirms earlier units and establishes their partial order. These sets of links form a directed acyclic graph, or DAG – similar to the blockchain.

Everyone is allowed to add a new unit to the database – as long as they sign the transaction and pay a fee equal to the size of the added data in bytes.

The fee is paid to other users, who later confirm the newly added unit by including its hash within their own units. As each new unit is added, each earlier unit receives more and more confirmations from later units that include its hash – either directly or indirectly.

Byteball’s system revolves around an internal currency called bytes. Bytes are used to pay for adding data to the database. You can also use Byteball to issue your own currencies. You might issue a currency that represents data stored on Byteball – like property rights, debt, or company shares.

The advantage of Byteball is that it creates a tamper-proof record of history. Byteball’s whitepaper mentions George Orwell’s 1984, where the protagonist Winston Smith works in the Records Department of the Ministry of Truth.

His job is to revise historical records to make the past conform to the government’s narrative – including removing people from history or deleting records from history. Byteball wants to prevent that from happening.

Basically, Byteball wants to bring the advantages of blockchain technology to database management. Today, that system has extended to meet the needs in a diverse range of markets.

### Byteball Features

Byteball offers all of the following features:

* #### Conditional Payments

  Byteball has one feature that you can’t get in traditional currencies – conditional payments. You set a condition when the payee receives the money. If the condition is not met, you get your money back.

* #### P2P Payments In Chat:

  You can chat and pay from the same messaging app. Sending a payment is as easy as sending a message.

* #### Prediction Markets:

  You can create a P2P smart contract that’s unlocked when a specific event occurs. Some people use this to bet on price movements. Others use it for insurance.

* #### P2P Insurance:

  Byteball lets you buy insurance from peers and then get paid when a negative event occurs. You can also sell insurance for profit. Insurance is just a simple smart contract that can be unlocked by the insured – if the event in question *did *occur – or unlocked by the insurer – if the event *did not *occur.

  You can insure against flight delay, for example, by finding your counterpart in the #P2P_insurance channel on Byteball’s Slack. Create a contract. If your flight arrives late, you can chat with the Byteball flight delays oracle to have it post the data about the delay, then unlock the contract.

* #### P2P Betting:

  You can bet against other users on sports events. Again, you find your counterpart in the #prediction_markets channel on the Byteball Slack, then create a contract that’s unlocked by you or your peer based on the outcome of the game.

* #### Chatbots:

  You can use Byteball to shop by chatting with a merchant’s bot, paying in just two clicks.

* #### Bot Store:

  Add and discover new chatbots from the Byteball online store. Developers can instantly access all Byteball users by adding their chatbot to the bot store. There are chatbots for sports scores, for example, flight delays, BTC prices, and more.

* #### Untraceable Currency Called Blackbytes:

  Want to pay in complete privacy? Byteball uses something called blackbytes, described as “a cash-like untraceable currency whose transactions are not visible on the public database, they are sent peer-to-peer instead.”


* #### Community Spirit:

  Byteball doesn’t have a central entity that stores and processes all payments. Instead, transactions created by users are cryptographically linked to one another. Once you add your new transaction, the number of other transactions that link to it grows like a snowball.


* #### Immutable Storage:

  As mentioned above, Byteball has an immutable storage system. Once data is added to Byteball, it can never be revised or removed.


* #### Settlement Finality:

  Once certain criteria are met, a new transaction becomes final. That transaction cannot be revised even by an attacker with large computational power.


* #### Regulated Assets:

  Byteball allows for the creation of regulated assets – like from financial institutions that need to meet KYC/AML requirements.


* #### Multi-Signature:

  You can choose to lock your funds behind multiple signatures.

### Conclusion

Byteball began as a system for decentralized immutable storage of arbitrary data – similar to other blockchains. Today, Byteball can be used to launch your own [digital currencies](https://bitcoinexchangeguide.com/cryptocurrency/), make bets with other users, and even buy insurance in a P2P marketplace. It’s a unique concept based on smart contracts, Slack, and blockchain technology.

<span style="color:silver;font-size:11px">Source: [bitcoinexchangeguide.com](https://bitcoinexchangeguide.com/byteball/)</span>

---

# BYTEBALL VS. IOTA

### 1. Who was first?

No one knows when the first idea of IOTA or Byteball came to the minds of  David Sønstebø, Come-from-Beyond, Sergui Popov of IOTA and Anton Churyumov of Byteball.

The former are the first “CORE” founders of IOTA who bring excellent abilities and a lot of expertise. Since IOTA has grown a lot, CORE  has grown with the addition of Dominik Schiener, Gianluigi Davassi and a few more experienced members of the IOTA-foundation.
Further info about new foundation-members can be found here: [https://forum.iotatoken.com/t/current-revealed-foundation-members/1098](https://forum.iotatoken.com/t/current-revealed-foundation-members/1098)

The latter, Anton Churyumov is well-known, a skilled scientist and developer in the scene -and the only developer of Byteball AFAIK.

Based on the announcements-threads on Bitcointalk and the date of the fully functioning main net of IOTA in July 2016, **it is safe to say that the first DAG aka the Tangle was IOTA-token. **

This doesn’t really give us more information about the intrinsic value of the tech itself but gives us an idea of what technology had more time to mature in terms of coding, testing and distribution. Especially when it comes to real-world adoption outside of Cryptoland. More about that in 4)

### 2. Technical differences and features

To underline the field of application of both technologies, this feature-table provides an easy comparison of the most important perks.

| *Features (simplified list)*  | **Byteball**                             | **IOTA-token**                           |
| ----------------------------- | ---------------------------------------- | ---------------------------------------- |
| Total amount                  | 10 ^15 BYTEnot-inflationary              | 2.779.530.283.277.761 iotanot-inflationary, high number for countless devices in the future |
| Mainnet                       | 25th December 2016                       | July 2016                                |
| Premine                       | 1%                                       | Zero premine                             |
| Transaction fees              | Yes (1:1 BYTE per Byte Data)             | no                                       |
| POW/POS                       | No POS/POW. Instead a Mainchain (MC) for including tx. | POW while generating addresses and any tx. |
| Unique features               | -Private asset: Blackbyte integrated for anonymous tx.–quantum secure NTRU algorithm can be added in the future. | No tx-fees especially for the Internet of things.-already quantum secure because hash-based Winternitz signatures. |
| Underlying tech               | DAG and scalable                         | DAG and scalable, branch-able for small devices needed in the IoT. |
| Theoretical confirmation-time | ~30s                                     | Quasi-infinitesimal. More nodes: faster network. |

### 3. Unique features

Apart from all advantages, a cryptocurrency can have, the underlying DAG is a big advantage both discussed technologies inherit.

This feature is kind of a preeminence in Cryptoland because traditional blockchains struggle with a lot of problems like scalability and speed with a growing amount of data.

* Byteball’s unique feature is without a doubt its integrated private asset, which allows conducting anonymous transactions with Blackbyte.
* IOTA’s unique feature is undoubtedly that no transaction-fees are taken. The only technology capable of functioning as the backbone of the Internet of Things on a global scale therefore is IOTA.

### 4. Real-world adoption and field of application

In my opinion, IOTA is still far away from “mass-adoption”, but also years ahead of Byteball. Months of negotiation and clever strategic management of the IOTA-CORE, especially David Sønstebø’s efforts and Dominik Schiener’s participations in meaningful IoT-conferences, lead to tons of collaborations and partnerings between IOTA and real companies.

The recently added foundation-members are the first glance at IOTA’s future, which is not stuck in Cryptoland, but located in real global businesses.

This is maybe the biggest winning margin IOTA has over Byteball at this moment, for speculators and developers.

The field of application is the most mentionable difference here.
Byteball is actively trying to replace existing currencies such as Bitcoin and, even if this sounds boastful: Dollar, Euro and all other FIAT-currencies, at least for the long run -like Bitcoin does.

IOTA can be used as such but has a completely different operational area: the IoT. The global network, where countless devices communicate with each other in domestic fields, in industrial appliances such as sensoring or M2M and for nano-payments where transactions-fees matter. Smart-contracts, smart-data, smart-cities are just a few examples of where IOTA can and will work.

### 5. Are Byteball and IOTA competitors?

To sum up: No. If Byteball would aim for being the IoT-ledger, one could conclude that IOTA is superior.
But Byteball’s field is set in currency-replacements, smart contracts, anonymous fast value-shifting.

**Byteball in fact, can do everything IOTA can do, except functioning as the backbone of the Internet of Things because transactions-fees would be counterproductive.**

<span style="color:silver;font-size:11px">Source: [tangleblog.com](http://www.tangleblog.com/2017/01/03/byteball-vs-iota-token/)</span>

---

Essentially, Byteball is built on “peer-to-peer” relations. While the same is true for many other cryptocurrencies, there is one major difference here – conditional payments. One of the problems that many have found when dealing with these digital currencies is that the other party can’t always be trusted to fulfill their end of the deal, and with an irreversible payment, this can have consequences. 

Byteball eliminates this problem by setting allowing parties to make a condition, that if left unfulfilled, will allow them to get their money back in a set period of time. An example of this would be setting the condition that in order for the other party to receive payment, they must first send a certain amount of bytes, and if they do not within the timeframe of four hours, your money is returned. For individuals who are exchanging bytes and want to make sure the other partner fulfills their part of the “contract”, Byteball has stood out against other cryptocurrencies with this idea.

Although the conditional payments may be the main attraction, Byteball also features no-fee crypto-exchanges, and blackbytes – which are for more private payments which won’t appear on a public database. There is also no central system that stores the payments with Byteball, but after a new transaction is made, it is cryptographically linked to other transactions – making a chain-like effect.

<span style="color:silver;font-size:11px">Source: [ftreporter.com](http://ftreporter.com/cryptocurrency-review-byteball-and-its-features/)</span>

---

[White paper](https://byteball.org/Byteball.pdf)