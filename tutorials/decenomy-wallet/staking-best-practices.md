---
description: Optimizing the process and overcoming common challenges
---

# ▪ Staking Best Practices

{% embed url="https://www.youtube.com/watch?v=aW2ubmbIFPY" %}

This guide explains how to optimize staking and solve the most common problems.

We open our wallet (in our case SAPP), and let's make sure staking is active.

<figure><img src="../../.gitbook/assets/staking active - open wallet.PNG" alt=""><figcaption></figcaption></figure>

**Staking optimization**

When staking, the larger the address balance the more will be earned. However, when we receive a reward, the coins are spent and it is necessary to wait for 600 confirmations to be available again for staking (mature)

It is therefore useful to divide the coins into different inputs through the **`setstakesplitthreshold`** command.

Whenever a successful stake is found, the stake amount is split across as many outputs (each with a value higher than the threshold) as possible.

E.g. If the coin stake input + the block stake reward is 30280, and the split threshold is 3400, the corresponding coinstake transaction will have 9 outputs (of 3400 SAPP each).

It is also possible to set the split value from the UI, Settings→Options→Wallet

<figure><img src="../../.gitbook/assets/stake split threshold.PNG" alt=""><figcaption></figcaption></figure>

Another useful command to know is **`setautocombinethreshold`**. Periodically the wallet will look for 'dust' in your addresses, and combine them up to the number of coins set in the configuration setting.&#x20;

The command **`setautocombinethreshold`**_**`true value`**_ will enable a feature that will automatically combine all staking / masternode rewards you receive into one input, up to the amount that you specify with the value.

So, if you want your minimum input size to be 5000 SAPP via the user interface, then you would want to follow the steps below:

1. Go to '**Settings**' from your wallet
2. &#x20;Select '**Options**'
3. Choose '**Wallet**' from the dropdown menu
4. &#x20;Check the '**Autocombine threshold**' checkbox to display the input box
5. &#x20;Enter a value (e.g. 5000)
6. &#x20;Click '**Save**' to store changes&#x20;

<figure><img src="../../.gitbook/assets/auto combine threshold.PNG" alt=""><figcaption></figcaption></figure>

Once done, any inputs less than 5000 will be swept into a new input, repetitively until the combined threshold is exceeded.

Once that threshold is exceeded, the grouping begins with another input. Your wallet MUST be unlocked when a reward is received for this to take effect.

### Common problems

We can check the staking status in detail with the following command **`getstakingstatus`**

<figure><img src="../../.gitbook/assets/get staking status.PNG" alt=""><figcaption></figcaption></figure>

Below is an explanation of the result of the command.

* "**staking\_status**": true|false, (boolean) whether the wallet is staking or not
* "**staking\_active**": true|false, (boolean) whether the wallet is active or not
* "**staking\_enabled**": true|false, (boolean) whether staking is enabled/disabled in sapphire.conf
* "**haveconnections**": true|false, (boolean) whether network connections are present
* "**mnsync**": true|false, (boolean) whether masternode data is synced
* "**walletunlocked**": true|false, (boolean) whether the wallet is unlocked
* "**stakeablecoins**": n, (numeric) number of stakeable UTXOs
* "**stakingbalance**": d, (numeric) SAPP value of the stakeable coins (minus reserve balance, if any)
* "**stakesplitthreshold**": d, (numeric) value of the current threshold for stake split
* "**lastattempt\_age**": n, (numeric) seconds since the last stake attempt
* "**lastattempt\_depth**": n, (numeric) depth of the block on top of which the last stake attempt was made
* "**lastattempt\_hash**": xxx, (hex string) hash of the block on top of which the last stake attempt was made
* "**lastattempt\_coins**": n, (numeric) number of stakeable coins available during the last stake attempt
* "**lastattempt\_tries**": n, (numeric) number of stakeable coins checked during the last stake attempt

For staking to be active, the first six values must necessarily be "true". Below we explain how to solve the most frequent problems you might encounter.

* **haveconnections**: if false, you don't have connections to the coin network. Make sure you have internet access, consider the port being blocked or bad connectivity.
* **walletunlocked**: if false, click the lock icon in the top right, select staking only, and enter your passphrase.
* **mnsync**: if false, wait 20 minutes. If still false, consider deleting mncache.dat and mnpayments.dat files from the data directory.
* **staking status**: if all of the above is True and this is still False, first try, close the wallet for 30 seconds, open and unlock (if encrypted), and wait 5 minutes.

That’s everything you need to know about staking.
