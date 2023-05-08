---
description: >-
  LoopX has launched the wallet credit score APIs on Injective with NFTs, SBTs
  and more on the roadmap!
---

# Injective Hackathon - Spring 2023

## Overview

We have analyzed 25,624 wallets on Injective chains to build:

* Wallet profiles with credit scores and interest profiles,
* NFTs and SBTs for you to collect, and
* AI network generated oracles on chain.

This will enable more innovative use cases onchain, such as DIDs, social DApps, gaming and beyond!



## Credit Score on Injective

### Score Distributions

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>Credit Score Histogram</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Score Scatter Plot</p></figcaption></figure>

### API Entpoints

#### Endpoint 1: /api/score-sdk/get-by-address/:address

* This API endpoint retrieves the credit score associated with a specific wallet address.

URL Parameters

* address (required): The wallet address to retrieve the credit score for.

HTTP Method

* GET

Example Request

```
GET http://app.loopx.network/api/score-sdk/get-by-address/inj1000rzgcxhfwk8xkq7zp5v3dl9f98ce6pp8dj3s
```

Example Response

```
[
    {
        "id": 10,
        "walletAddress": "inj1000rzgcxhfwk8xkq7zp5v3dl9f98ce6pp8dj3s",
        "creditScore": 0.759141,
        "valueScore": 0,
        "tags": "",
        "modelId": 0,
        "modelName": "",
        "chainId": 888,
        "chainName": "Injective",
        "createTime": "2023-04-26T18:34:26.060Z",
        "updateTime": "2023-04-26T18:44:57.713Z"
    }
]
```

#### Endpoint 2: /api/score-sdk/get-by-address-chain/:address/:chainId

This API endpoint retrieves the credit score associated with a specific wallet address on a specific blockchain.

URL Parameters

* address (required): The wallet address to retrieve the credit score for.
* chainId (required): The ID of the blockchain to retrieve the credit score on. For example, Injective is 888

HTTP Method

* GET

Example Request

```
GET http://app.loopx.network/api/score-sdk/get-by-address-chain/inj1000rzgcxhfwk8xkq7zp5v3dl9f98ce6pp8dj3s/888
```

Example Response

```
[
    {
        "id": 10,
        "walletAddress": "inj1000rzgcxhfwk8xkq7zp5v3dl9f98ce6pp8dj3s",
        "creditScore": 0.759141,
        "valueScore": 0,
        "tags": "",
        "modelId": 0,
        "modelName": "",
        "chainId": 888,
        "chainName": "Injective",
        "createTime": "2023-04-26T18:34:26.060Z",
        "updateTime": "2023-04-26T18:44:57.713Z"
    }
]
```

## Roadmap

We will launch the following by end of May, 2023:

* AI network oracle smart contracts deployment,
* NFTs and SBTs with community badges for you to collect, and
* Injective ecosystem projects integrations.

After that, we will build anything the Injective community hoping us to build!
