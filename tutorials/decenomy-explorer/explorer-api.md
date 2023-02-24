---
description: >-
  This documentation is intended to provide information on the available methods
  to extract data from DECENOMY Explorer using its API.
---

# ▪ Explorer API

Being a public API, there is no need to use any kind of authentication.

\
[<mark style="color:blue;">API v1</mark>](explorer-api.md#api-v1-endpoint-url) reports plain text.\
\
[<mark style="color:blue;">API v2</mark>](explorer-api.md#api-v2-endpoint-url) reports more info in detail.



## API v1 Endpoint URL

<mark style="color:blue;">https://explorer.decenomy.net/api/v1/coins/</mark><mark style="color:red;">coin</mark><mark style="color:blue;">/</mark>

### Path parameters v1

| Name |  Type  | Description                                           | Info     |
| ---- | :----: | ----------------------------------------------------- | -------- |
| coin | string | should be replaced by the coin ticker, always in caps | Required |

### Query parameters v1

| Name           |  Type  | Description                                               | Info     |
| -------------- | :----: | --------------------------------------------------------- | -------- |
| getblockcount  | string | Plain block count, just the block number value            | Optional |
| getmoneysupply | string | Supply - circulating supply, just the supply number value | Optional |

### Example query v1

```
https://explorer.decenomy.net/api/v1/coins/SAPP/getblockcount
```

### Example response v1

```
1987842
```

## API v2 Endpoint URL

<mark style="color:blue;">https://explorer.decenomy.net/api/v2/</mark><mark style="color:red;">coin</mark><mark style="color:blue;">/</mark>

### Path parameters v2

| Name |  Type  | Description                                           |   Info   |
| ---- | :----: | ----------------------------------------------------- | :------: |
| coin | string | should be replaced by the coin ticker, always in caps | Required |

### Query parameters v2

| Name             |  Type  | Description                                                                                          | Info     |
| ---------------- | :----: | ---------------------------------------------------------------------------------------------------- | -------- |
| blocks           | string | <p>Last 30 blocks - blockhash tx /<br>/ blocktime / height / confirmations</p>                       | Optional |
| transactions     | string | <p>Last 30 blocks - blockhash / blocktime / height / tx /<br>confirmations / recipients / amount</p> | Optional |
| peers            | string | Full information of peers available                                                                  | Optional |
| masternodes      | string | Full information of each masternode in the network                                                   | Optional |
| info             | string | Wallet and blockchain information                                                                    | Optional |
| masternode/count | string | Total number of masternodes connected in the network                                                 | Optional |
| status           | string | Status of blockchain based in last block received                                                    | Optional |

### Example query v2

```
https://explorer.decenomy.net/api/v2/SAPP/info
```

### Example response v2

```
{
  "response": {
    "connections": 171,
    "errors": "",
    "blocks": 1987846,
    "paytxfee": 0,
    "moneysupply": 1224915018.8013475,
    "difficulty": 527924.3523641471,
    "keypoolsize": 100,
    "keypoololdest": 1627317470,
    "walletversion": 169900,
    "timeoffset": 0,
    "testnet": false,
    "version": 1050100,
    "staking status": "Staking Inactive",
    "protocolversion": 70931,
    "services": "NETWORK/BLOOM/",
    "balance": 0,
    "relayfee": 0.0001,
    "proxy": ""
  },
  "success": true
}
```
