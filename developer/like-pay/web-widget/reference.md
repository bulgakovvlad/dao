---
description: LIKE pay web widget API Reference
---

# Reference

## Introduction

This is still a feature under active development and testing, and not meant for production use for general public, please contact us if you are interested.

## Formatting the widget URL

### Base URL

Testnet: [`https://rinkeby.like.co/in/widget/pay`](https://rinkeby.like.co/in/widget/pay)  
Production: [`https://like.co/in/widget/pay`](https://like.co/in/widget/pay)\`\`

###  Input Params

| Query String | Description |
| :--- | :--- |
| to | Target Liker ID |
| amount | amount of LIKE token to be given to target Liker ID |
| via | \(optional\) Liker ID of agent/platform |
| fee | \(optional\) extra LIKE token paid to agent/platform as fee |
| remarks | \(optional\) public remarks to be written onto LikeCoin chain |
| state | \(optional\) local state to be passed back after payment success, used for data/security purpose |
| redirect\_uri | \(optional\) redirect user to uri after payment success/failed   |
| blocking | \(optional\) default false, wait until payment is confirmed before redirecting |

### Output Params

| Query String | Description |
| :--- | :--- |
| tx\_hash | transaction hash of resulting payment, verify status using transaction status query API |
| state | locale state that was passed as input, used for data/security purpose |
| remarks | remarks passed as input params |

### Transaction query API

Cosmos LCD: `https://api.like.co/cosmos/lcd/txs/${txHash}`

\(TODO\) like.co API: `https://api.like.co/txs/id/${txHash}`

### Example Link

Following links are in testnet.

#### Input Link:[`https://rinkeby.like.co/in/widget/pay?to=ckxpress&amount=1&via=kiutest0&fee=1&state=123&redirect_uri=http%3A%2F%2Flocalhost%3A3000`](https://rinkeby.like.co/in/widget/pay?to=ckxpress&amount=1&via=kiutest0&fee=1&state=123&redirect_uri=http%3A%2F%2Flocalhost%3A3000)

#### Redirect result:

#### [`http://localhost:3000/?tx_hash=DAD08549E31744C8EA8DE27AC2F2DC691960D424CC7D589B9B904355AB8FDB15&state=123`](http://localhost:3000/?tx_hash=DAD08549E31744C8EA8DE27AC2F2DC691960D424CC7D589B9B904355AB8FDB15&state=123)

#### Tx Status Query:[`https://api.rinkeby.like.co/cosmos/lcd/txs/DAD08549E31744C8EA8DE27AC2F2DC691960D424CC7D589B9B904355AB8FDB15`](https://api.rinkeby.like.co/cosmos/lcd/txs/DAD08549E31744C8EA8DE27AC2F2DC691960D424CC7D589B9B904355AB8FDB15)
