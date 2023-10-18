# ▪ Staking statistics on VaultWatch

{% embed url="https://youtu.be/BdBH4GapqOo" %}

In this guide, we will explain various useful VaultWatch features and provide instructions on how to utilize them.

Let's go to the web page [<mark style="color:blue;">https://vaultwatch.eu/</mark>](https://vaultwatch.eu/)\


![](<../.gitbook/assets/0 (1) (1) (1)>)

To locate your desired coin, simply enter its name into the search bar. For the purpose of this tutorial, we will use SAPP as our demonstration coin.

Click on the coin's name to go to the next page

<figure><img src="../.gitbook/assets/sapp vaultwatch.PNG" alt=""><figcaption></figcaption></figure>

Once this is done, we can see the basic information of the coin (e.g. links and some technical details) as shown in the image below:

<figure><img src="../.gitbook/assets/sapp details.PNG" alt=""><figcaption></figcaption></figure>

We will focus on staking and show you the main tools offered by VaultWatch.

* Profit Calculator
* Staking Information
* Best Staking Addresses\


**Profit Calculator**

The profit calculator provides an estimate of the rewards you can anticipate based on a specified amount of coins (this statistic is not 100% guaranteed as the blockchain is a dynamic system in which the factors change constantly).

As shown in the image below, we have input a value of 30 000 SAPP:

<figure><img src="../.gitbook/assets/sapp profit calculator.PNG" alt=""><figcaption></figcaption></figure>

* **Stake, not compounding**: expected returns on a daily, weekly, monthly, and annual basis without restaking our rewards.
* **Stake, compounding**: expected returns on a daily, weekly, monthly, and annual basis restaking our rewards.
* **In masternode (collateral 200000)**: Comparison between our staking rewards and the rewards of a masternode.
* **In shared masternode (fee 6%)**: Comparison between our staking rewards and an investment in a shared masternode.

At the time of writing this guide, a staking reward is equivalent to 280 SAPP, while the daily rewards table is approximately 66 SAPP.

This means an average of about 0.24 rewards per day.\


**Staking Information**

<figure><img src="../.gitbook/assets/sapp staking info.PNG" alt=""><figcaption></figcaption></figure>

* **Average input size**: The average amount of coins per input in the network
* **Average input weight**: The average age of inputs

The age of the inputs for the DECENOMY coins is not a factor that affects the probability of receiving a reward. The only determining factor is the size of an input.

As we have seen in the guide [<mark style="color:blue;">Staking Best Practices</mark>](../tutorials/decenomy-wallet/staking-optimization-and-common-problems.md) it can be useful to change the value of **setstakesplitthreshold** to avoid having a too large quantity of coins in an immature state (100 confirmations).

Apparently, all our coins, after receiving the first reward, will not be available for staking for about 100 minutes.

<figure><img src="../.gitbook/assets/immature coins.PNG" alt=""><figcaption></figcaption></figure>

\
**Best Staking Addresses**

<figure><img src="../.gitbook/assets/sapp best staking addresses.PNG" alt=""><figcaption></figcaption></figure>

In this last section, we see the same statistics as before, but referring to the individual addresses of the largest active stakers on the network.

We can therefore use an average input size value as a reference value for the **`setstakesplitthreshold`** in our wallet, from the debug console.

Alternatively, you can adjust the stake split threshold value from your wallet's interface. Navigate to '**Settings**,' then '**Options,**' and select '**Wallet**.'&#x20;

Within the wallet section, you will find the option to manually input the desired value. Remember to save your changes once you are finished.

<figure><img src="../.gitbook/assets/stake split threshold (1).PNG" alt=""><figcaption></figcaption></figure>

After a while we will see that the coins in an immature state will be about <mark style="background-color:red;">3400 SAPP,</mark> leaving the rest of the balance free.

As seen in the image below, only a small portion of our coins are immature. This allows us the potential for a slight increase in rewards.\


![](<../.gitbook/assets/8 (1) (1)>)
