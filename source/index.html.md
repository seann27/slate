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

> Make sure to replace `meowmeowmeow` with your API key.

Btiformance uses API keys to allow access to the API. You can register a new Btiformance API key by creating an account on [Our Website](https://www.bitformance.com) and navigating to the [API Keys Dashboard](https://www.bitformance.com/API-Dashboard) once logged in.

<aside class="notice">
Replace <code>your_api_key_here</code> and <code>your_api_secret_key_here</code> with your actual API credentials.
</aside>

# Endpoints

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

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
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
