# 🔸 Staking statistics on VaultWatch

{% embed url="https://youtu.be/BdBH4GapqOo" %}

### Staking statistics on VaultWatch <a href="#_u6z1i9e4rptx" id="_u6z1i9e4rptx"></a>

In this guide, we'll walk you through some useful VaultWatch features and how to use them.

Let's go to the web page [https://vaultwatch.eu/](https://vaultwatch.eu/)\


![](<../.gitbook/assets/0 (1) (1) (1)>)

In the search bar we look for the coin that interests us, in this case we use OWO as an example.

Click on the coin name to go to the next page

![](<../.gitbook/assets/1 (1) (1) (1)>)

Once this is done we can see the basic information of the coin (links and some technical details) as shown in the image.

In this guide we focus on staking and show you the main tools offered by VaultWatch.

* Profit Calculator
* Staking Information
* Best Staking Addresses

![](<../.gitbook/assets/2 (1) (1) (1)>)

**Profit Calculator**

The profit calculator offers an estimate of the rewards that we can expect given a certain amount of coins (this statistic is not 100% guaranteed as the blockchain is a dynamic system in which the factors change constantly).

As we can see in the image we have entered the value of 1 million OWO.

* Stake, not compounding: expected returns on a daily, weekly, monthly and annual basis without restaking our rewards.
* Stake, compounding: expected returns on a daily, weekly, monthly and annual basis restaking our rewards.
* In masternode (collateral 100000): Comparison between our staking rewards and the rewards of a masternode.
* In shared masternode (fee 6%): Comparison between our staking rewards and an investment in a shared masternode.

At the time of writing this guide, a staking reward is equivalent to 25 OWO, while the daily rewards table is about 550 OWO.

This means an average of about 22 rewards per day.

![](<../.gitbook/assets/3 (1) (1) (1)>)

**Staking Information**

![](<../.gitbook/assets/4 (1)>)

* Average input size: The average amount of coins per input in the network
* Average input weight: The average age of inputs

The age of the inputs for the DECENOMY coins is not a factor that affects the probability of receiving a reward.

The only determining factor is the size of an input.

As we have seen in the guide "Staking optimization and common problems" it can be useful to change the value of setstakesplitthreshold to avoid to have a too large quantity of coins in immature state (100 confirmations).

As we can see in our wallet all of our coins, after receiving the first reward, will not be available for staking for about 100 minutes.

![](<../.gitbook/assets/5 (1) (1)>)

**Best Staking Addresses**

![](<../.gitbook/assets/6 (1) (1)>)

In this last section we see the same statistics as before, but referring to the individual addresses of the largest active stakers on the network.

We can therefore use an average input size value as a reference value for the setstakesplitthreshold in our wallet, from the debug console.

![](<../.gitbook/assets/7 (1) (1)>)

After a while we will see that the coins in an immature state will be about 3500, leaving the rest of the balance free.

In this way our chances of receiving a reward will slightly increase.

As we can see from the image only a small part of our coins are immature.

By doing so we have the possibility of having a slight increase in reward.

![](<../.gitbook/assets/8 (1) (1)>)
