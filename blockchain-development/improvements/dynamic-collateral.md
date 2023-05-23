# Dynamic Collateral

DSW is a cryptocurrency platform based on PIVX, which is also based on DASH. DSW is part of DECENOMY, a project network that shares the same wallet codebase and blockchain infrastructure. DSW stands for Decenomy Standard Wallet and enables cross-chain interoperability and governance among the DECENOMY projects.

One of the features that DSW supports is changing collateral values for masternodes, opposite to DASH and PIVX where the collateral is constant. Masternodes are special nodes that provide services to the network. To run a masternode, one must lock a specific amount of DECENOMY coins as collateral. The collateral amount is currently determined by a fixed table specifying the collateral value for each block height range. However, this fixed system has some disadvantages, such as:

* It does not reflect the dynamic changes in the market conditions and user preferences, which may affect the supply and demand of DECENOMY coins and masternodes.
* It does not allow for fine-tuning of the collateral amount to achieve an optimal balance between risk and reward for masternode operators and investors.
* It may create barriers to entry or exit for masternode operators, who may need to acquire or dispose of a large number of coins to meet the collateral requirements or the assembly of an abnormal number of masternodes.
* It may cause an unbalance of masternode numbers on the network, creating an excess of computational weight on the normal network functioning, and an excess of operational costs for the masternode operator.

To overcome these limitations, a new feature called Dynamic Collaterals is proposed. Dynamic Collateral is a feature that will change the collateral value at every 100000 blocks, evaluating the current coin supply, a predefined target percentage of the supply locked in masternodes, and the desired number of masternodes in the network. The idea behind Dynamic Collaterals is to adjust the collateral amount according to the market conditions and the network needs, ensuring a balance between supply and demand, security, and decentralization.

The change in collateral value will be limited by a minimum percentage and a maximum percentage, for example, if we have a percentage range of 10% and 20% means that in each collateral change the value will change only within that range or not at all. The changes are also valid for supply reduction in cases when a certain quantity of coins gets burned within the running period. These changes are also limited in terms of value steps, they will only change in steps of 1000 coins. The moment that this calculation takes place is on the block created 7 days before the collateral change, giving time for the investor to adjust their masternodes accordingly for the next epoch.

For example, suppose that the current coin supply is 1 billion DSW, the target percentage of locked supply in masternodes is 70%, and the desired number of masternodes is 2880, which means that each masternode should receive a reward every alternate day (assuming 60 seconds per block). Then, the collateral amount can be calculated as follows:

Collateral = (Coin Supply x Target Percentage) / Desired Number of Masternodes Collateral = (1 billion x 70%) / 2880 Collateral = 243055 DSW

This means that to run a masternode, one needs to lock 243000 DSW coins as collateral (rounded down to a multiple of 1000 coins). This amount will be valid for 100000 blocks, after which it will be recalculated based on the new coin supply, target percentage, and desired number of masternodes.

Suppose that after 100000 blocks, the coin supply has increased to 1.3 billion DSW due to new minting, and the target percentage and desired number of masternodes remain unchanged. Then, the new collateral amount can be calculated as follows:

Collateral = (Coin Supply x Target Percentage) / Desired Number of Masternodes Collateral = (1.3 billion x 70%) / 2880 Collateral = 315972 DSW

This means that to run a masternode, one needs to lock 315000 DSW coins as collateral (rounded down to a multiple of 1000 coins). However, since this amount exceeds the maximum percentage change of 20%, it will be capped at 291600 DSW (243000 x 1.2); in this case, 291000 DSW coins a multiple of 1000 coins. This amount will be valid for another 100000 blocks.

The benefits of Dynamic Collaterals are:

* It allows for more flexibility and adaptability of the network to changing market conditions and user preferences.
* It encourages more participation and investment in masternodes by adjusting the collateral amount to an optimal level that balances risk and reward.
* It creates more opportunities for masternode operators, who can benefit from price fluctuations and arbitrage possibilities.
* In the future, it will aid the adaptation of the DSW coins to the actual market, by using real-world metrics to fine-tune the algorithm's parameters.

Dynamic Collaterals is still a work in progress and a small component of the overall DECENOMY vision and may require further research and testing before implementation. However, it is an exciting and promising feature that may bring more value and utility to the DSW platform and the DECENOMY network.
