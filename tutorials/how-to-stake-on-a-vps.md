# How to stake on a VPS

{% embed url="https://www.youtube.com/watch?v=7xZ4z480T3Q" %}



### How to stake on a VPS <a href="#_gjfles2s8o27" id="_gjfles2s8o27"></a>

In this guide we are going to explain how to stake on a VPS server.

This guide is for advanced users and assumes that you know how to safely use an Ubuntu server.

We assume that you will run all the commands as **root** user.\


First we need to connect to our server via SSH and download the wallet we want to install, from our official links on GitHub.

In this case we have chosen KYAN.

The wallet links can be found at [https://github.com/kyancoin/KYAN/releases](https://github.com/kyancoin/KYAN/releases)

We choose the Linux version and copy the link.

To download the wallet we use **wget** command.

**wget https://github.com/kyancoin/KYAN/releases/download/v1.0.0.1/KYAN-1.0.0.1-Linux.zip**

![](<../.gitbook/assets/0 (1)>)

We now extract the archive using **unzip** command (if the command is not available you can run **apt install unzip**)\
**unzip KYAN-1.0.0.1-Linux.zip**\
\
![](<../.gitbook/assets/1 (2)>)\


Now we copy the KYAN executables in /usr/local/bin folder to make them available as system command

**cp kyanite\* /usr/local/bin/**

![](<../.gitbook/assets/2 (1)>)

Let’s start the KYAN daemon and encrypt the wallet.

**kyanited -daemon**

**kyanite-cli encryptwallet “YOUR-PASSWORD-HERE”**

![](<../.gitbook/assets/3 (1) (1)>)

We can now create a system service to make sure our wallet will always run.\
**nano /etc/systemd/system/kyanite.service**

This command will open nano text editor where we paste the following.

\[Unit]

Description=KYAN service

After=network.target

StartLimitIntervalSec=0

\[Service]

Type=forking

Restart=always

RestartSec=10

User=root

ExecStart=/usr/local/bin/kyanited -conf=/root/.kyanite/kyanite.conf -datadir=/root/.kyanite

ExecStop=-/usr/local/bin/kyanite-cli -conf=/root/.kyanite/kyanite.conf -datadir=/root/.kyanite stop

\[Install]

WantedBy=multi-user.target\


![](<../.gitbook/assets/4 (2)>)

![](<../.gitbook/assets/5 (1)>)

We can now exit nano and save (ctrl+x, y, enter).

To apply the change we run this command\
**systemctl daemon-reload**

![](../.gitbook/assets/6)

Now we need to setup the kyanite.conf file, we use nano again

**nano /root/.kyanite/kyanite.conf**\


Paste the following lines in it:\


daemon=1\
server=1\
rpcuser=kyanite\
rpcpassword=YOUR-RPC-PASS\
rpcallowip=127.0.0.1

staking=1

![](../.gitbook/assets/7)

Save and exit nano.\


The configuration is now complete and we can start the kyanite service and generate a new address.

**systemctl start kyanite.service**

**kyanite-cli getnewaddress**

![](<../.gitbook/assets/8 (1)>)

While we wait for the wallet synchronisation we can transfer our funds to the address we just generated.

![](../.gitbook/assets/9)

As the last step we need to unlock our wallet for staking.\
**kyanite-cli walletpassphrase “YOUR-PASSWORD-HERE” 99999999999999 true**

![](../.gitbook/assets/10)

**N.B. Coins need 600 network confirmations to start staking**

You can verify staking status using the command below

**kyanite-cli getstakingstatus**

All the fields must return “true”

It is highly recommended to delete terminal history when we enter sensitive information like wallet passwords.\
It can be done simply using **history -c** command.
