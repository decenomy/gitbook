---
description: >-
  A major improvement for the masternode system and for DECENOMY coins as a
  whole.
---

# Last Paid V2

## **Introducing Last Paid V2**

One of the features of the masternode system is the ability to track when a masternode (MN) was last paid. This information is helpful for determining the order of payments and the expected time until the next payment. \
\
However, the previous standard method of calculating the last paid value of an MN has some flaws and inaccuracies that can affect the fairness and efficiency of the payment system. \
\
_**The last paid v2 is a new feature that aims to solve these problems and improve the accuracy and reliability of the last paid value.**_



## Challenges and limitations of the standard version

The previous standard method of calculating the last paid value of an MN is based on the number of votes that an MN receives from other MNs in the network. \
\
The inherited masternode system uses a voting mechanism to select which MN will receive the next payment. Each MN casts a vote for another MN that it thinks should be paid next based on various criteria, such as the last paid value, the protocol version, and the collateral age. \
\
The MN that receives the most votes in a given block is selected as the winner and is elected to be paid.

However, this voting mechanism has some drawbacks and limitations.&#x20;

* It relies on the assumption that all MNs are online and voting correctly, which may not always be accurate. Some MNs may be offline, malfunctioning, or maliciously voting for themselves or their possible colluding partners.&#x20;
* It does not account for the actual time when an MN was paid but only for the votes it received. This means that sometimes an MN may lose a payment round because it received fewer votes than another MN, even though it was truthfully waiting longer to be paid.&#x20;
* It does not provide a clear and consistent way to measure the last paid value of an MN across different nodes in the network. Different nodes may have different views of the voting history and may disagree on which MN was last paid and when.

## **Introducing a Blockchain-based solution**

The last paid v2 is a new feature that addresses these issues and replaces the old voting mechanism entirely. \
\
_**Instead of using votes to determine when an MN was paid, it uses the blockchain itself as the source of truth.**_

* The blockchain tracks and records every payment made to an MN in a field called `payee`.
* The last paid v2 algorithm scans the blockchain from the most recent to the oldest block and looks for this field to identify when an MN was paid.
* It then assigns a last-paid value to each MN based on the block height of its last payment.

This way, **it can accurately and objectively determine which MN was waiting longer to be paid** and select it as the next winner.

## **Advantages of Last Paid V2**

The last paid v2 has several advantages over the old voting mechanism.

1. It does **not depend on external factors** such as network connectivity, node availability, or voting behavior. It only relies on the blockchain data, which is immutable and verifiable by anyone. \

2. It reflects the actual time when an MN was paid, not just the number of votes it received. This **ensures that every MN has a fair chance to receive a payment** based on its waiting time, not popularity, influence, or luck. \

3. **Provides a consistent and transparent way to measure the last paid value of an MN** across different nodes in the network. Every node can easily calculate and verify this value by scanning the same blockchain data.

The **last paid v2 is a significant improvement for the masternode system** and for DECENOMY coins as a whole. It enhances the accuracy and reliability of the payment system, increases its fairness and efficiency, and reduces its complexity and potential for errors. \
\
It also makes DECENOMY coins more attractive and competitive as a cryptocurrency that rewards its users for securing and supporting its network.
