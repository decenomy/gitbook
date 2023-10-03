---
description: These are commands we introduce periodically in each wallet update
---

# Commands

* **`checkconnection`** RPC call: This call allows you to test the connectivity of your server with other nodes on the network.\

* **`mnping`** RPC call\`: This call allows you to send a ping message to your masternode and receive a pong response. It helps you verify that your masternode is online and responsive.\

* **`reloadmasternodeconfig`** RPC call and a corresponding GUI element: This call and element allow you to reload your masternode configuration file from the command line or the user interface. It is useful if you want to make changes to your masternode settings without stopping or restarting them.\

* **`setautocombinethreshold`** command and UI support: This command replaces the deprecated `autocombinerewards` command, which automatically combines small inputs into larger ones to reduce transaction fees and improve privacy. The new command allows you to set a threshold amount for auto-combining inputs and enable or disable this feature from the command line or the user interface.\

* **`rewindblockindex`** command, start option, and the GUI element: This command allows you to rewind your block index in case of a fork or a corrupted database. It deletes all blocks after a specified height and re-syncs with the network from that point. It can help you recover from various issues that may affect your wallet functionality or integrity.\

* **`getactivemasternodecount`** RPC/CLI command: The command reports the number of active masternodes of a wallet.
