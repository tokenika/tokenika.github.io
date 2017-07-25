## Byteball: Just like Iota, it uses tangles but with the difference that Iota is specialized for machine-to-machine use, while Byteball is specialized for human-to-human applications. They seem much complementary.

Unbounded scalability, fast confirmations, no miners, no blocks, low fees.

Byteball data is stored and ordered using [directed acyclic graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph) (DAG) rather than blockchain. This allows all users to secure each other's data by referencing earlier data units created by other users, and also removes scalability limits common for blockchains, such as blocksize issue.

Blockless design is simpler because there are no blocks, there are only transactions. Users just add their transactions to the end of the DAG themselves, they don't have to wait when miners create a new block and there is no guesswork whether miners will include your transaction in the block.

The consensus algorithm used to protect from double-spends is based on establishing a total order within the DAG. This is achieved by selecting a chain, called main chain, which gravitates towards units issued by commonly recognized reputable users — witnesses. See the [white paper](https://byteball.org/Byteball.pdf) for details.

## Core features

#### Atomic exchange

When two parties sign a single unit that executes both legs of the exchange, the two transactions either happen simultaneously or don't happen at all. It is no longer necessary to trust any centralized exchanges.

#### Regulated assets

Regulated institutions can issue assets that are compatible with KYC/AML requirements. Every transfer of such asset is to be cosigned by the issuer, and if there is anything that contradicts the regulations, the issuer won't cosign.

#### Multi signature

For security, you can require that your funds be spendable only when several signatures are provided, e.g. from your laptop and from your phone. For shared control of funds, signatures from different people may be required.

#### On-chain oracles

When dealing with untrusted counterparties, you can lock the funds on an address that is spendable either by you or by the counterparty, depending on the events registered to the database by trusted data providers — oracles.

#### Immutable storage

Once stored in the Byteball database, the data can neither be revised nor removed.

#### Settlement finality

After certain criteria are met, a new transaction becomes final. It cannot be revised even by a powerful attacker. No guesswork about the right number of confirmations, no 51% attacks.

> Source: https://byteball.org/

---

# BYTEBALL VS. IOTA

## 1. Who was first?

No one knows when the first idea of IOTA or Byteball came to the minds of  David Sønstebø, Come-from-Beyond, Sergui Popov of IOTA and Anton Churyumov of Byteball.

The former are the first “CORE” founders of IOTA who bring excellent abilities and a lot of expertise. Since IOTA has grown a lot, CORE  has grown with the addition of Dominik Schiener, Gianluigi Davassi and a few more experienced members of the IOTA-foundation.
Further info about new foundation-members can be found here: [https://forum.iotatoken.com/t/current-revealed-foundation-members/1098](https://forum.iotatoken.com/t/current-revealed-foundation-members/1098)

The latter, Anton Churyumov is well-known, a skilled scientist and developer in the scene -and the only developer of Byteball AFAIK.

Based on the announcements-threads on Bitcointalk and the date of the fully functioning main net of IOTA in July 2016, **it is safe to say that the first DAG aka the Tangle was IOTA-token. **

This doesn’t really give us more information about the intrinsic value of the tech itself but gives us an idea of what technology had more time to mature in terms of coding, testing and distribution. Especially when it comes to real-world adoption outside of Cryptoland. More about that in 4)

## 2. Technical differences and features

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

## 3. Unique features

Apart from all advantages, a cryptocurrency can have, the underlying DAG is a big advantage both discussed technologies inherit.

This feature is kind of a preeminence in Cryptoland because traditional blockchains struggle with a lot of problems like scalability and speed with a growing amount of data.

* Byteball’s unique feature is without a doubt its integrated private asset, which allows conducting anonymous transactions with Blackbyte.
* IOTA’s unique feature is undoubtedly that no transaction-fees are taken. The only technology capable of functioning as the backbone of the Internet of Things on a global scale therefore is IOTA.

## 4. Real-world adoption and field of application

In my opinion, IOTA is still far away from “mass-adoption”, but also years ahead of Byteball. Months of negotiation and clever strategic management of the IOTA-CORE, especially David Sønstebø’s efforts and Dominik Schiener’s participations in meaningful IoT-conferences, lead to tons of collaborations and partnerings between IOTA and real companies.

The recently added foundation-members are the first glance at IOTA’s future, which is not stuck in Cryptoland, but located in real global businesses.

This is maybe the biggest winning margin IOTA has over Byteball at this moment, for speculators and developers.

The field of application is the most mentionable difference here.
Byteball is actively trying to replace existing currencies such as Bitcoin and, even if this sounds boastful: Dollar, Euro and all other FIAT-currencies, at least for the long run -like Bitcoin does.

IOTA can be used as such but has a completely different operational area: the IoT. The global network, where countless devices communicate with each other in domestic fields, in industrial appliances such as sensoring or M2M and for nano-payments where transactions-fees matter. Smart-contracts, smart-data, smart-cities are just a few examples of where IOTA can and will work.

## 5. Are Byteball and IOTA competitors?

To sum up: No. If Byteball would aim for being the IoT-ledger, one could conclude that IOTA is superior.
But Byteball’s field is set in currency-replacements, smart contracts, anonymous fast value-shifting.

**Byteball in fact, can do everything IOTA can do, except functioning as the backbone of the Internet of Things because transactions-fees would be counterproductive.**

> Source: http://www.tangleblog.com/2017/01/03/byteball-vs-iota-token/