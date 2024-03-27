# Dynamic Rewards

Dynamic Rewards represents one of the most recent updates introduced by Decenemy, designed to fine-tune our network's block reward mechanism and how coin supply is calculated, ultimately aiming to strengthen stability and sustainability.

With this recent development, block rewards will now be adjusted proportionally according to both the total and circulating supply within the network. This adjustment is essential for preserving the economic stability and sustainability of the network.

Given the dependency of block rewards on coin supply, a sophisticated Circulating Supply Algorithm has been implemented. This enhanced algorithm will guarantee precise supply calculations by:

* Analyzing the entire Unspent Transaction Output (UTXO) set.&#x20;
* Excluding burn addresses and UTXOs matching the current and upcoming masternode collateral values.&#x20;
* Counting UTXOs based on their age, fully counting those less than three months old, linearly scaling down those between three to twelve months, and excluding all UTXOs older than twelve months.

Additionally, there has been an enhancement in monitoring supply dynamics. The updated metric provides an efficient method for monitoring coin supply and implementing required adjustments to emission rates when necessary. For example, once the exact values of the total and circulating supplies are determined, the system computes the emission rate for the current period. This process also involves anticipating expected minting, determined by specified percentages of the total and circulating supplies.

To streamline the reward adjustment process, Decenomy introduces a damping function. This function moderates any changes in the block reward (delta value) through a linear approach, ranging from 0% to 10% with each adjustment.
