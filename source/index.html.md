---
title: XBTS Market API v2

language_tabs: # must be one of https://git.io/vQNgJ

- json
  #- shell
  #- javascript

toc_footers:

- <a href='https://ex.xbts.io'>XBTS DEX</a>
- <a href='https://app.xbts.io'>XBTS DeFi</a>
- <a href='https://github.com/xbts/market-api-v2'>Documentation source</a>

includes:

- errors

search: true

code_clipboard: true

meta:

- name: description
  content: XBTS DEX Market API v2

---

# Introduction

Welcome to the XBTS Free Market API! You can use our API to access XBTS DEX API endpoints, which can get information on
market assets, trade pairs, order book, tickers, trade history from blockchain.

**Data is broadcasted from the blockchain!**

API endpoint `https://cmc.xbts.io/api/v2/`

# Summary

_Overview of market data for all tickers & all markets._

**Request URL** <span class='badge'>GET</span> ` https://cmc.xbts.io/v2/summary`

**About Data:**

* **tickers** - All market tickers with unified_cryptoasset_id (ucid)
* **assets** - All listed XBTS assets with unified_cryptoasset_id (ucid)
* **total** - Count trade pairs & assets

> The above command returns JSON structured like this:

```json
{
  "tickers": {
    "BTS_STH": {
      "base_id": 463,
      "quote_id": 5602,
      "base_symbol": "BTS",
      "quote_symbol": "STH",
      "last": "0.18800000",
      "sell": "0.20408163",
      "buy": "0.18800000",
      "base_volume": "306.34583",
      "quote_volume": "1635.48191",
      "change": "1.34",
      "type": "spot",
      "isFrozen": 0,
      "url": "https://ex.xbts.io/market/XBTSX.STH_BTS"
    },
    "USDT_BTC": {
      "base_id": 825,
      "quote_id": 1,
      "base_symbol": "USDT",
      "quote_symbol": "BTC",
      "last": "31438.94939968",
      "sell": "31438.94939968",
      "buy": "31255.93000000",
      "base_volume": "5957.699194",
      "quote_volume": "0.19573896",
      "change": "0.75",
      "type": "spot",
      "isFrozen": 0,
      "url": "https://ex.xbts.io/market/XBTSX.BTC_XBTSX.USDT"
    }
  },
  "assets": {
    "STH": {
      "name": "SmartHoldem",
      "ucid": 5602,
      "can_withdraw": true,
      "can_deposit": true,
      "min_withdraw": 10,
      "max_withdraw ": 0,
      "maker_fee": 0.1,
      "taker_fee": 0.1,
      "id": "4099",
      "precision": 6,
      "decimals": 8,
      "prefix": "XBTSX.",
      "active": true
    },
    "CNY": {
      "name": "bitCNY",
      "ucid": -1,
      "can_withdraw": false,
      "can_deposit": false,
      "min_withdraw": 1,
      "max_withdraw ": 0,
      "maker_fee": 0,
      "taker_fee": 0,
      "id": "113",
      "precision": 4,
      "decimals": 4,
      "prefix": "",
      "active": true
    },
    "DOGE": {
      "name": "Dogecoin",
      "ucid": 74,
      "can_withdraw": true,
      "can_deposit": true,
      "min_withdraw": 200,
      "max_withdraw ": 0,
      "maker_fee": 0.1,
      "taker_fee": 0.2,
      "id": "4156",
      "precision": 5,
      "decimals": 8,
      "prefix": "XBTSX.",
      "active": true
    },
    "BTC": {
      "name": "Bitcoin",
      "ucid": 1,
      "can_withdraw": true,
      "can_deposit": true,
      "min_withdraw": 0.005,
      "max_withdraw ": 0,
      "maker_fee": 0.1,
      "taker_fee": 0.1,
      "id": "4157",
      "precision": 8,
      "decimals": 8,
      "prefix": "XBTSX.",
      "active": true
    },
    "ETH": {
      "name": "Ethereum",
      "ucid": 1027,
      "can_withdraw": true,
      "can_deposit": true,
      "min_withdraw": 0.015,
      "max_withdraw ": 0,
      "maker_fee": 0.1,
      "taker_fee": 0.1,
      "id": "4760",
      "precision": 7,
      "decimals": 18,
      "prefix": "XBTSX.",
      "active": true
    }
  },
  "total": {
    "pairs": 288,
    "assets": 60
  }
}
```

# Assets

**_Display all listed coins & tokens_**

**Request URL** <span class='badge'>GET</span> `https://cmc.xbts.io/v2/assets`

**About Return Data:**

* **name** - Asset name
* **ucid** - Unique ID of cryptocurrency assigned by Unified Cryptoasset ID. According to specification
  coinmarketcap.com
* **id** - BitShares Blockchain registered internal Asset ID ex. https://bts.ai/asset/XBTSX.STH id = 1.3.4099
* **prefix** - Blockchain asset internal prefix **XBTSX.**ASSET matches all **XBTS DEX** assets in the **BitShares**
  blockchain ex. https://ex.xbts.io/market/XBTSX.STH_XBTSX.BTC or https://ex.xbts.io/asset/XBTSX.STH

> The above command returns JSON structured like this:

```json
{
  "STH": {
    "name": "SmartHoldem",
    "ucid": 5602,
    "can_withdraw": true,
    "can_deposit": true,
    "min_withdraw": 10,
    "max_withdraw ": 0,
    "maker_fee": 0.1,
    "taker_fee": 0.1,
    "id": "4099",
    "precision": 6,
    "decimals": 8,
    "prefix": "XBTSX.",
    "active": true
  },
  "BTS": {
    "name": "BitShares",
    "ucid": 463,
    "can_withdraw": true,
    "can_deposit": true,
    "min_withdraw": 0.1,
    "max_withdraw ": 0,
    "maker_fee": 0,
    "taker_fee": 0,
    "id": "0",
    "precision": 5,
    "decimals": 5,
    "prefix": "",
    "active": true
  },
  "BTC": {
    "name": "Bitcoin",
    "ucid": 1,
    "can_withdraw": true,
    "can_deposit": true,
    "min_withdraw": 0.005,
    "max_withdraw ": 0,
    "maker_fee": 0.1,
    "taker_fee": 0.1,
    "id": "4157",
    "precision": 8,
    "decimals": 8,
    "prefix": "XBTSX.",
    "active": true
  },
  "USDT": {
    "name": "TetherUSD",
    "ucid": 825,
    "can_withdraw": true,
    "can_deposit": true,
    "min_withdraw": 10,
    "max_withdraw ": 0,
    "maker_fee": 0.08,
    "taker_fee": 0.08,
    "id": "5589",
    "precision": 6,
    "decimals": 6,
    "prefix": "XBTSX.",
    "active": true
  }
}
```

# Tickers

## All Tickers

**_Summary of all tickers_**

**Request URL** <span class='badge'>GET</span> `https://cmc.xbts.io/v2/tickers`

**About Return Data:**

* **base_id** - Unique Base ID of cryptocurrency assigned by Unified Cryptoasset ID. According to specification
  coinmarketcap.com
* **quote_id** - Unique Quote ID of cryptocurrency assigned by Unified Cryptoasset ID. According to specification
  coinmarketcap.com

> The above command returns JSON structured like this:

```json
{
  "timestamp": 1654634804,
  "ticker": {
    "BTS_STH": {
      "base_id": 463,
      "quote_id": 5602,
      "base_symbol": "BTS",
      "quote_symbol": "STH",
      "last": "0.18800000",
      "sell": "0.20408163",
      "buy": "0.18800000",
      "base_volume": "306.34583",
      "quote_volume": "1635.48191",
      "change": "1.34",
      "type": "spot",
      "isFrozen": 0,
      "url": "https://ex.xbts.io/market/XBTSX.STH_BTS"
    },
    "USDT_USDC": {
      "base_id": 825,
      "quote_id": 3408,
      "base_symbol": "USDT",
      "quote_symbol": "USDC",
      "last": "1.01000000",
      "sell": "1.01000000",
      "buy": "0.99000000",
      "base_volume": "254.824794",
      "quote_volume": "253.676391",
      "change": "0",
      "type": "spot",
      "isFrozen": 0,
      "url": "https://ex.xbts.io/market/XBTSX.USDC_XBTSX.USDT"
    },
    "USDT_HIVE": {
      "base_id": 825,
      "quote_id": 5370,
      "base_symbol": "USDT",
      "quote_symbol": "HIVE",
      "last": "0.60027678",
      "sell": "0.59979400",
      "buy": "0.59520900",
      "base_volume": "5597.333138",
      "quote_volume": "9523.454411",
      "change": "8.13",
      "type": "spot",
      "isFrozen": 0,
      "url": "https://ex.xbts.io/market/XBTSX.HIVE_XBTSX.USDT"
    }
  },
  "totalPairs": 288
}
```

This endpoint retrieves all tickers.

## Ticker

**_Get specific ticker_**

**Request URL** <span class='badge'>GET</span> `https://cmc.xbts.io/v2/tickers/BTS_STH`

**Request Data:**

ticker - as USDT_BTC

**About Return Data:**

* **base_id** - Unique Base ID of cryptocurrency assigned by Unified Cryptoasset ID. According to specification
  coinmarketcap.com
* **quote_id** - Unique Quote ID of cryptocurrency assigned by Unified Cryptoasset ID. According to specification
  coinmarketcap.com

> The above command returns JSON structured like this:
>

```json
{
  "BTS_STH": {
    "base_id": 463,
    "quote_id": 5602,
    "base_symbol": "BTS",
    "quote_symbol": "STH",
    "last": "0.18800000",
    "sell": "0.20408163",
    "buy": "0.18800000",
    "base_volume": "306.34583",
    "quote_volume": "1635.48191",
    "change": "1.34",
    "type": "spot",
    "isFrozen": 0,
    "url": "https://ex.xbts.io/market/XBTSX.STH_BTS",
    "timestamp": 1654640489
  }
}
```

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted": ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

