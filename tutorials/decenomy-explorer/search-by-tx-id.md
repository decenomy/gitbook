---
description: How to understand the Tx ID information from DECENOMY Explorer
---

# ▪ Search by Tx ID

The search box can be found in all tabs, allowing for precise queries on the explorer.

<figure><img src="../../.gitbook/assets/Explorer search box.jpg" alt=""><figcaption></figcaption></figure>

After utilizing the aforementioned search box to obtain more information regarding a specific transaction ID, or when clicking on the transaction value presented on block details ( please check [<mark style="color:blue;">Search by Block and/or Hash</mark>](search-by-block-and-or-hash.md#detailed-block-info) guide ) the user will be redirected to a screen resembling the following:

### <mark style="background-color:red;">Detailed Tx ID info, case 1</mark>

This screen displays comprehensive and detailed information about the events that took place in this specific block, on this specific transaction.

<figure><img src="../../.gitbook/assets/Explorer tx detail_v1.jpg" alt=""><figcaption></figcaption></figure>

#### <mark style="background-color:red;">Section 1 from Tx ID info, case 1</mark>

This section provides cross-information about the transaction ID, including the block height to which it belongs, as well as the hash and time of that particular block height.



#### <mark style="background-color:red;">Section 2 from Tx ID info, case 1</mark>

The " Sending Address " indicates that it was a reward transaction created, taking into consideration the nature of the coin, POS/MN.\
\
The " Recipients " section indicates that the address receiving the 280 SAPP was a stake reward, while the address receiving the 520 SAPP was a masternode reward. Further confirmation of these values is explained in the next section.



#### <mark style="background-color:red;">Section 3 from Tx ID info, case 1</mark>

To provide some context for the information presented, it's important to briefly explain the staking process. In this process, a certain amount of inputs with a specific value are ready to stake a block. Once staked, the input that earns the reward is compounded with its previous amount and the stake reward value.

In the " Input Details " section, it's indicated that the input with an amount of 11214 SAPP was staked in this block. After the stake, the same input with the same address now has a compounded value of 11494 SAPP, as shown in the " Output Details " section.

It's worth noting that in some cases, a wallet can stake and split one input into multiple inputs, as seen in the example presented in the following board.

<figure><img src="../../.gitbook/assets/Explorer stake and splitting.jpg" alt=""><figcaption></figcaption></figure>

The wallet in this case staked with an input of 44699 SAPP and compounded it into a new input. At the same time, it split this new input into four others.

By referring to sections 2 and 3, it is always possible to gain insight into the reward value that a stake and a masternode receive, as well as what happens when an address stakes.



### <mark style="background-color:red;">Detailed Tx ID info case 2</mark>

This type of transaction is a breakdown of a coin transfer and is not related to any reward earned from a masternode or stake.&#x20;

<figure><img src="../../.gitbook/assets/Explorer tx_3 detail.jpg" alt=""><figcaption></figcaption></figure>

The " Sending Address " indicates that the transaction used a combination of 5 different wallet addresses to transfer the desired value.\
\
As for the "Recipients" address, it appears that the user wanted to transfer precisely 5112 SAPP to one address while sending the remaining amount of 1.9078 SAPP to another address.\
It is important to note that this value already takes into account the deduction of transaction fees.
