---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Bitformance API
---

# Introduction

Welcome to the Bitformance API! You can use our API to access cryptocurrency data that powers the [Bitformance](https://www.bitformance.com) website, including information on various coins, market trends, and historical data.

We offer language bindings in Shell, JavaScript, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples using the tabs in the top right.

To access the API, you'll need both an API-KEY and an API-SECRET-KEY. Free API keys are available to all users with limited calls per month and restricted access to certain endpoints. For additional access and higher usage limits, please contact the Bitformance Team at contact@bitformance.com.

This API documentation page was created with [Slate](https://github.com/slatedocs/slate).

# Authentication

> To authorize, use this code:

```python
import requests

url = "https://api.bitformance.com/api/v2/api_endpoint_here"
headers = {
    "API-KEY": "your_api_key_here",
    "API-SECRET-KEY": "your_api_secret_key_here"
}

response = requests.get(url, headers=headers)
print(response.json())
```

```shell
curl "https://api.bitformance.com/api/v2/api_endpoint_here" \
  -H "API-KEY: your_api_key_here" \
  -H "API-SECRET-KEY: your_api_secret_key_here"
```

```javascript
const fetch = require('node-fetch');

const url = "https://api.bitformance.com/api/v2/api_endpoint_here";
const headers = {
    "API-KEY": "your_api_key_here",
    "API-SECRET-KEY": "your_api_secret_key_here"
};

fetch(url, { headers })
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

> Make sure to replace `your_api_key_here` and `your_api_secret_key_here` with your API key and your Secret Key.

Btiformance uses API keys to allow access to the API. You can register a new Btiformance API key by creating an account on [Our Website](https://www.bitformance.com) and navigating to the [API Keys Dashboard](https://www.bitformance.com/API-Dashboard) once logged in.

<aside class="notice">
Replace <code>your_api_key_here</code> and <code>your_api_secret_key_here</code> with your actual API credentials.
</aside>

# Endpoints

## Get Browsable Indexes

```python
import requests

url = "https://api.bitformance.com/api/v2/get-browsable-indexes"
headers = {
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_api_secret_key"
}

response = requests.get(url, headers=headers)
indexes = response.json()
```

```shell
curl "https://api.bitformance.com/api/v2/get-browsable-indexes" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_api_secret_key"
```

```javascript
const axios = require('axios');

let config = {
  headers: {
    'API-KEY': 'your_api_key',
    'API-SECRET-KEY': 'your_api_secret_key'
  }
};

axios.get('https://api.bitformance.com/api/v2/get-browsable-indexes', config)
  .then(response => {
    let indexes = response.data;
  });
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": [
    {
      "index_info": {
        "_id": "65569daf76cd9d2bc8ec55b5",
        "created": "2023-11-16 22:54:38.948000",
        "updated": "2024-08-24 12:01:06.870000",
        "initial_timestamp": 1483315200,
        "name": "50/50 Bitcoin + Ethereum",
        "description": "50/50 Bitcoin + Ethereum with a monthly rebalance and an initial starting balance of $1,000.",
        "algorithm": "standard",
        "asset_type": "fixed",
        "weighting_method": "equal_weight",
        "rebalancing_interval": "monthly",
        "custom_weights": {}
      },
      "index_holdings": [
        {
          "ticker": "BTC",
          "id": 1,
          "quantity": 2.3096153033332625
        },
        {
          "ticker": "ETH",
          "id": 1027,
          "quantity": 46.162267242963296
        }
      ],
      "index_performance": {
        "marketcap": 1595252377661.0916,
        "initial_value": "1000",
        "value": 275182.10313638713,
        "drawdown": -33.3143,
        "change_24hour": 12337.86948527029,
        "change_7d": 19450.525573806197,
        "changepct_24hour": 4.693985222307298,
        "changepct_7d": 7.605836463057204,
        "change_1m": -37412.106191677856,
        "change_3m": -55245.7049836932,
        "change_6m": 24564.655092169764,
        "change_1y": 138708.6350380197,
        "changepct_1m": -11.968265910010562,
        "changepct_3m": -16.719447826744783,
        "changepct_6m": 9.801653988526661,
        "changepct_1y": 101.63780328205716,
        "asset_new_highs": 0,
        "asset_new_lows": 0,
        "asset_performance_24h_bearish": 2,
        "asset_performance_24h_bullish": 0,
        "asset_sma_200d_over": 1,
        "asset_sma_200d_under": 1,
        "asset_sma_50d_over": 1,
        "asset_sma_50d_under": 1,
        "asset_1y_high": 0,
        "asset_1y_low": 0,
        "asset_alltime_high": 0,
        "asset_alltime_low": 0
      }
    }
  ]
}
```

This endpoint retrieves all available browsable indexes.

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-browsable-indexes`

### Query Parameters

<aside class="notice">
No query parameters are required for this endpoint.
</aside>

### Headers

Header | Description
--------- | ------- | -----------
API-KEY | Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>

## Get All Coins

```python
import requests

url = "https://api.bitformance.com/api/v2/get-all-coins"
headers = {
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_secret_key"
}
params = {
    "page": 1  # Example page parameter
}

response = requests.get(url, headers=headers, params=params)
coins = response.json()
```

```shell
curl "ttps://api.bitformance.com/api/v2/get-all-coins?page=1" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_secret_key"
```

```javascript
const fetch = require('node-fetch');

let url = 'https://api.bitformance.com/api/v2/get-all-coins?page=1';
let options = {
  method: 'GET',
  headers: {
    'API-KEY': 'your_api_key',
    'API-SECRET-KEY': 'your_secret_key'
  }
};

fetch(url, options)
  .then(response => response.json())
  .then(data => console.log(data));
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": [
    {
      "coin_id": 1,
      "coin_slug": "bitcoin",
      "name": "Bitcoin",
      "symbol": "BTC",
      "description": "",
      "tier_lvl_1": "Digital Currency",
      "tier_lvl_2": "General",
      "last_updated": "2024-08-25T22:12:00.000Z",
      "price": 64510.34179357949,
      "market_cap": 1273762311113.9631,
      "volume": 17528186093.072506,
      "last_daily_close": 64176.36706695918,
      "all_time_high": 73079.3733787985,
      "all_time_low": 0.04951,
      "avg_price_200d": 63241.400978283695,
      "avg_price_50d": 61652.955475512186,
      "change_24hour": 65334.582599120564,
      "changepct_24hour": 1.27768786,
      "change_7day": 69978.65742318358,
      "changepct_7day": 8.4766496,
      "one_year_high": 73079.3733787985,
      "one_year_low": 25684.019423324316,
      "weekly_high": 64176.36706695918,
      "weekly_low": 58482.74531725411
    }
  ]
}
```

This endpoint retrieves data for a list of coins. This endpoint is paginated, returning 100 coins at a time.

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-all-coins`

### Query Parameters

Parameter | Type | Description
--------- | -----------
page | integer | Specifies the page number to retrieve (e.g., 1, 2, 3, etc.).

### Headers

Header | Description
API-KEY	| Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>

## Get Coin Data

```python
import requests

url = "https://api.bitformance.com/api/v2/get-coin-data"
headers = {
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_secret_key"
}
params = {
    "symbol": "BTC"  # Example coin symbol
}

response = requests.get(url, headers=headers, params=params)
coin_data = response.json()
```

```shell
curl "https://api.bitformance.com/api/v2/get-coin-data?symbol=BTC" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_secret_key"
```

```javascript
const fetch = require('node-fetch');

let url = 'https://api.bitformance.com/api/v2/get-coin-data?symbol=BTC';
let options = {
  method: 'GET',
  headers: {
    'API-KEY': 'your_api_key',
    'API-SECRET-KEY': 'your_secret_key'
  }
};

fetch(url, options)
  .then(response => response.json())
  .then(data => console.log(data));
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "cmc_id": 1,
    "symbol": "BTC",
    "name": "Bitcoin",
    "marketcap": 1275614678405.117,
    "volume": 17575445269.965878,
    "price": 64604.15587964322,
    "change_24hour": 65292.934075997626,
    "change_7day": 70188.21847699354,
    "changepct_24hour": 1.06615153,
    "changepct_7day": 8.64350369,
    "daily_graph_data": {
      "dates": [1279324800, 1279411200, 1279497600],
      "price": [64247.746095482005, 64251.68477402696, 64332.30054186885]
    },
    "description": "",
    "tier_lvl_1": "Digital Currency",
    "tier_lvl_2": "General",
    "initial_value": 0.04951
  }
}
```

This endpoint retrieves information and graph data for a specific coin.

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-coin-data`

### Query Parameters

Parameter | Type | Description
--------- | -----------
symbol | string | The symbol of the coin to retrieve (e.g., BTC).

### Headers

Header | Description
API-KEY	| Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>

## Get Top 50 Index

```python
import requests

url = "https://api.bitformance.com/api/v2/get-top50-index"
headers = {
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_secret_key"
}

response = requests.get(url, headers=headers)
top50_index = response.json()
```

```shell
curl "https://api.bitformance.com/api/v2/get-top50-index" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_secret_key"
```

```javascript
const fetch = require('node-fetch');

let url = 'https://api.bitformance.com/api/v2/get-top50-index';
let options = {
  method: 'GET',
  headers: {
    'API-KEY': 'your_api_key',
    'API-SECRET-KEY': 'your_secret_key'
  }
};

fetch(url, options)
  .then(response => response.json())
  .then(data => console.log(data));
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "index_info": {
      "_id": "6478bf4fc7a3444d2433fd36",
      "created": "2022-06-12 20:09:13.368000",
      "updated": "2024-08-25 22:31:06.880000",
      "initial_timestamp": 1491004800,
      "name": "Bitformance Altcoin",
      "description": "Top 200 Altcoins - weighted by market cap, rebalanced quarterly, and an initial starting balance of $1,000. This index aims to reflect the overall performance/trends of altcoins.",
      "algorithm": "top_ranked",
      "asset_type": "dynamic",
      "weighting_method": "market_cap",
      "rebalancing_interval": "QUARTERLY",
      "custom_weights": {}
    },
    "index_holdings": [
      { "ticker": "LTC", "id": 2, "quantity": 3.287725841392287 },
      { "ticker": "XRP", "id": 52, "quantity": 2450.9797025951802 },
      { "ticker": "DOGE", "id": 74, "quantity": 6378.512439581647 }
    ],
    "daily_graph_data": {
      "dates": [1491004800, 1491091200, 1491177600],
      "prices": [1000.0, 1004.5596183364022, 1639.5754208146486]
    },
    "constituent_info": [
      {
        "coin_id": 2,
        "coin_slug": "litecoin",
        "name": "Litecoin",
        "symbol": "LTC",
        "description": "",
        "tier_lvl_1": "Digital Currency",
        "tier_lvl_2": "General",
        "last_updated": "2024-08-25T22:28:00.000Z",
        "price": 65.30661265643441,
        "market_cap": 4891647320.7893,
        "volume": 232839669.20519465,
        "last_daily_close": 66.58131223228845,
        "all_time_high": 386.45077919,
        "all_time_low": 1.1570099592,
        "avg_price_200d": 78.53544956180635,
        "avg_price_50d": 66.90979366661023,
        "change_24hour": 64.33712188532131,
        "changepct_24hour": -1.4845216,
        "change_7day": 64.30490964026299,
        "changepct_7day": -1.53384623,
        "one_year_high": 109.2439422366925,
        "one_year_low": 55.98397579556809,
        "weekly_high": 66.58131223228845,
        "weekly_low": 63.83114086015394
      },
      {
        "coin_id": 52,
        "coin_slug": "xrp",
        "name": "XRP",
        "symbol": "XRP",
        "description": "",
        "tier_lvl_1": "Digital Currency",
        "tier_lvl_2": "General",
        "last_updated": "2024-08-25T22:28:00.000Z",
        "price": 0.602992014999058,
        "market_cap": 33876148537.34648,
        "volume": 868473452.3078357,
        "last_daily_close": 0.6131096346343136,
        "all_time_high": 3.3778100014,
        "all_time_low": 0.00281020998955,
        "avg_price_200d": 0.5491737517745484,
        "avg_price_50d": 0.5612696043649822,
        "change_24hour": 0.5969002438476169,
        "changepct_24hour": -1.01025735,
        "change_7day": 0.6345072478846009,
        "changepct_7day": 5.22647599,
        "one_year_high": 0.7180356979709985,
        "one_year_low": 0.4198230598452304,
        "weekly_high": 0.6131096346343136,
        "weekly_low": 0.563904427330128
      },
      {
        "coin_id": 74,
        "coin_slug": "dogecoin",
        "name": "Dogecoin",
        "symbol": "DOGE",
        "description": "",
        "tier_lvl_1": "Digital Currency",
        "tier_lvl_2": "General",
        "last_updated": "2024-08-25T22:28:00.000Z",
        "price": 0.064202,
        "market_cap": 8453459345.12345,
        "volume": 345123456.12345,
        "last_daily_close": 0.065432,
        "all_time_high": 0.731578,
        "all_time_low": 0.0000869,
        "avg_price_200d": 0.062345,
        "avg_price_50d": 0.064123,
        "change_24hour": 0.063876,
        "changepct_24hour": -0.8734,
        "change_7day": 0.063789,
        "changepct_7day": -0.7564,
		"one_year_high": 0.089456,
		"one_year_low": 0.055432,
		"weekly_high": 0.065432,
		"weekly_low": 0.063432
	  }
    ]
  }
}
```

Returns 24-hour graph data for the top 50 ETF index.

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-top50-index`

### Query Parameters

<aside class="notice">
No query parameters are required for this endpoint.
</aside>

### Headers

Header | Description
API-KEY	| Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>

## Get Sector Indexes

```python
import requests

# Define the base URL and query parameters
base_url = "https://api.bitformance.com/api/v2/get-sector-indexes"
params = {
    "weighting_method": "market_cap",
    "sector": "Smart Contract Platform",
    "industry": "Layer 1"
}

# Send the GET request
response = requests.get(base_url, headers={
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_secret_key"
}, params=params)

sector_indexes = response.json()
```

```shell
# Define the base URL and query parameters
base_url="https://api.bitformance.com/api/v2/get-sector-indexes"
weighting_method="market_cap"
sector="Smart Contract Platform"
industry="Layer 1"

# Send the GET request using curl
curl -G "$base_url" \
  --data-urlencode "weighting_method=$weighting_method" \
  --data-urlencode "sector=$sector" \
  --data-urlencode "industry=$industry" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_secret_key"
```

```javascript
const fetch = require('node-fetch');

// Define the base URL and query parameters
const baseUrl = 'https://api.bitformance.com/api/v2/get-sector-indexes';
const params = new URLSearchParams({
    weighting_method: 'market_cap',
    sector: 'Smart Contract Platform',
    industry: 'Layer 1'
});

// Send the GET request
fetch(`${baseUrl}?${params.toString()}`, {
    method: 'GET',
    headers: {
        'API-KEY': 'your_api_key',
        'API-SECRET-KEY': 'your_secret_key'
    }
})
.then(response => response.json())
.then(data => console.log(data));
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": [
    {
      "index_info": {
        "_id": "664606b78fb1b7408916ea0d",
        "created": "2024-05-16 09:14:31.416000",
        "updated": "2024-08-25 23:21:05.883000",
        "initial_timestamp": 1483315200,
        "name": "Smart Contract Platform - Layer 1",
        "description": "SECTOR: Smart Contract Platform, INDUSTRY: Layer 1",
        "algorithm": "sector_ranked",
        "asset_type": "dynamic",
        "weighting_method": "market_cap",
        "rebalancing_interval": "quarterly",
        "custom_weights": {}
      },
      "index_holdings": [
        { "ticker": "ETH", "id": 1027, "quantity": 53.23441698627238 },
        { "ticker": "ETC", "id": 1321, "quantity": 65.43618871475672 },
        { "ticker": "NEO", "id": 1376, "quantity": 31.243727330472407 }
      ],
      "index_performance": {
        "marketcap": 596204330702.7146,
        "initial_value": 1000,
        "value": 263284.91562438454,
        "drawdown": -38.2951,
        "change_24hour": 1426.1018434149446,
        "change_7d": 20551.16186894165,
        "changepct_24hour": 0.5446071578892128,
        "changepct_7d": 8.466544743359915,
        "change_1m": -34404.563054258586,
        "change_3m": -62158.741309680394,
        "change_6m": 7523.415830343787,
        "change_1y": 133197.01240484312,
        "changepct_1m": -11.557198194229242,
        "changepct_3m": -19.09969359835266,
        "changepct_6m": 2.941574801681345,
        "changepct_1y": 102.3900063790364,
        "asset_new_highs": 12,
        "asset_new_lows": 1,
        "asset_performance_24h_bearish": 37,
        "asset_performance_24h_bullish": 13,
        "asset_sma_200d_over": 7,
        "asset_sma_200d_under": 43,
        "asset_sma_50d_over": 34,
        "asset_sma_50d_under": 16,
        "asset_1y_high": 1,
        "asset_1y_low": 0,
        "asset_alltime_high": 0,
        "asset_alltime_low": 0
      }
    }
  ]
}
```

Returns sector-specific indexes.

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-sector-indexes`

### Query Parameters

Parameter | Type | Description
--------- | -----------
weighting_method | string | Specifies the method of weighting (options are "market_cap" or "equal_weight").
sector | string | Specifies the sector to filter by (e.g., "Smart Contract Platform").
industry | string | Specifies the industry within the sector (e.g., "Layer 1").

<aside class="notice">
If no parameters are provided, the response will include all sector-specific indexes.
</aside>

### Headers

Header | Description
API-KEY	| Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>

## Get Altcoin Season Indicator

```python
import requests

# Define the base URL
base_url = "https://api.bitformance.com/api/v2/get-altcoin-season"

# Send the GET request
response = requests.get(base_url, headers={
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_secret_key"
})

altcoin_season = response.json()
```

```shell
# Define the base URL
base_url="https://api.bitformance.com/api/v2/get-altcoin-season"

# Send the GET request using curl
curl -X GET "$base_url" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_secret_key"
```

```javascript
const fetch = require('node-fetch');

// Define the base URL
const baseUrl = 'https://api.bitformance.com/api/v2/get-altcoin-season';

// Send the GET request
fetch(baseUrl, {
    method: 'GET',
    headers: {
        'API-KEY': 'your_api_key',
        'API-SECRET-KEY': 'your_secret_key'
    }
})
.then(response => response.json())
.then(data => console.log(data));
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "daily_graph_data": {
      "dates": [1491091200, 1491177600, 1491264000],
      "prices": [0.3333333333333333, 0.2857142857142857, 0.4285714285714285]
    }
  }
}
```

Returns date/price data of the altcoin season indicator

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-altcoin-season`

### Query Parameters

<aside class="notice">
No query parameters are required for this endpoint.
</aside>

### Headers

Header | Description
API-KEY	| Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>

## Get Taxonomies

```python
import requests

# Define the base URL
base_url = "https://api.bitformance.com/api/v2/get-taxonomies"

# Send the GET request
response = requests.get(base_url, headers={
    "API-KEY": "your_api_key",
    "API-SECRET-KEY": "your_secret_key"
})

taxonomies = response.json()
```

```shell
# Define the base URL
base_url="https://api.bitformance.com/api/v2/get-taxonomies"

# Send the GET request using curl
curl -X GET "$base_url" \
  -H "API-KEY: your_api_key" \
  -H "API-SECRET-KEY: your_secret_key"
```

```javascript
const fetch = require('node-fetch');

// Define the base URL
const baseUrl = 'https://api.bitformance.com/api/v2/get-taxonomies';

// Send the GET request
fetch(baseUrl, {
    method: 'GET',
    headers: {
        'API-KEY': 'your_api_key',
        'API-SECRET-KEY': 'your_secret_key'
    }
})
.then(response => response.json())
.then(data => console.log(data));
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "Smart Contract Platform": {
      "Layer 1": [
        {
          "coin_id": 268,
          "coin_slug": "whitecoin",
          "name": "WhiteCoin",
          "symbol": "XWC",
          "description": "",
          "tier_lvl_1": "Smart Contract Platform",
          "tier_lvl_2": "Layer 1",
          "last_updated": "2024-08-25T23:54:00.000Z",
          "price": 0.006833462117392149,
          "market_cap": 5222983.3594693085,
          "volume": 276653.98947512,
          "last_daily_close": 0.006772623798930958,
          "all_time_high": 2.59460633,
          "all_time_low": 0.00008236819849,
          "avg_price_200d": 0.014513675930935997,
          "avg_price_50d": 0.005160290346883868,
          "change_24hour": 0.006894846944956285,
          "changepct_24hour": 0.89829762,
          "change_7day": 0.007604938428139358,
          "changepct_7day": 11.28968446,
          "one_year_high": 0.06586916268536099,
          "one_year_low": 0.0032548452443409382,
          "weekly_high": 0.006772623798930958,
          "weekly_low": 0.005791444063172019
        },
        {
          "coin_id": 541,
          "coin_slug": "syscoin",
          "name": "Syscoin",
          "symbol": "SYS",
          "description": "",
          "tier_lvl_1": "Smart Contract Platform",
          "tier_lvl_2": "Layer 1",
          "last_updated": "2024-08-25T23:57:00.000Z",
          "price": 0.14032754085720214,
          "market_cap": 111219347.5380037,
          "volume": 14604079.80853925,
          "last_daily_close": 0.14858885341308029,
          "all_time_high": 1.2644112581040534,
          "all_time_low": 0.00021023600129,
          "avg_price_200d": 0.1762910427666894,
          "avg_price_50d": 0.10176526416675025,
          "change_24hour": 0.1327124349332593,
          "changepct_24hour": -5.42666527,
          "change_7day": 0.19936088658758805,
          "changepct_7day": 42.06825358,
          "one_year_high": 0.33628337715772594,
          "one_year_low": 0.06747341746601306,
          "weekly_high": 0.15948240628018331,
          "weekly_low": 0.09877473490429092
        },
        {
          "coin_id": 1027,
          "coin_slug": "ethereum",
          "name": "Ethereum",
          "symbol": "ETH",
          "description": "",
          "tier_lvl_1": "Smart Contract Platform",
          "tier_lvl_2": "Layer 1",
          "last_updated": "2024-08-25T23:58:00.000Z",
          "price": 2748.4704443622136,
          "market_cap": 330636478610.6457,
          "volume": 9381067892.878712,
          "last_daily_close": 2768.615443493595,
          "all_time_high": 4812.0876135348,
          "all_time_low": 0.4348289967,
          "avg_price_200d": 3252.1611123627804,
          "avg_price_50d": 2982.518385561687,
          "change_24hour": 2728.472024264639,
          "changepct_24hour": -0.72761998,
          "change_7day": 2889.0490443679905,
          "changepct_7day": 5.11479395,
          "one_year_high": 4066.690353397678,
          "one_year_low": 1540.9732397056287,
          "weekly_high": 2768.615443493595,
          "weekly_low": 2573.834787768792
        }
      ]
    }
  }
}
```

Returns taxonomy information for all relevant cryptocurrencies.

### HTTP Request

`GET https://api.bitformance.com/api/v2/get-taxonomies`

### Query Parameters

<aside class="notice">
No query parameters are required for this endpoint.
</aside>

### Headers

Header | Description
API-KEY	| Your unique API key.
API-SECRET-KEY | Your API secret key.

<aside class="success"> Authentication is required to access this endpoint. </aside>
