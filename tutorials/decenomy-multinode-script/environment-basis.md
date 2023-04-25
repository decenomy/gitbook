---
description: >-
  Proper file installation and user ID creation for secure environment
  deployment.
---

# ▪ Environment basis

The installation of the files provided by this script has been done properly, taking into account the best security practices.\
\
As a result, the files are not installed at the root level, as is common with similar tools. Instead, each instance of the coin installation will create its own user ID on the Linux system files, with the coin name serving as the identifier for the deployment location of the respective coin blockchain files.\
\
Please note the exact file locations using the coin sapphire as an example.

| Description                       | Directory                | Example ( when need )          |
| --------------------------------- | ------------------------ | ------------------------------ |
| $HOME directory                   | /home/users/             | -                              |
| Directory of user ID              | /home/users/userID/      | /home/users/sapphire/          |
| Wallet files location for user id | /home/users/userID/.coin | /home/users/sapphire/.sapphire |
| Daemon location                   | /usr/local/bin/          | -                              |
| Service files directory           | /etc/systemd/system/     | -                              |

In case you need to have access to the mentioned directories and files via a terminal, please follow the next steps:\


| Description           | Command     | Example       |
| --------------------- | ----------- | ------------- |
| To enter in userID    | su - userID | su - sapphire |
| To logout from userID | exit        | exit          |
