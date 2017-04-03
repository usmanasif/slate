---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Pronoun.io uses API keys to allow access to the API. You can register at [pronoun.io](https://pronoun-io.herokuapp.com) to get your API keys.

**Pronoun.io API expects for the following API keys to be included in all API requests to the server in a header :**

  * **access_id** -> Your access_id at registered with pronoun.io

  * **time** -> The time at which you make the API call

  * **content-md5** -> This is the hex digest generated using the time stamp and your secret-key(auth_token) from pronoun.io


<aside class="notice">
You must replace the values of above <code>variables</code> with your personal API keys in the header of every request of the provided code.
</aside>

# Wallet

## Get Wallet Credit

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/wallets/get_wallet_credit")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = Your Access_id
request["time"] = Time.now
request["content-md5"] = Your Content-MD5

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/wallets/get_wallet_credit"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: Your Access_id" -H "Time: Time.now" -H "CONTENT-MD5: Your Content-MD5" "https://pronoun-io.herokuapp.com/api/v1/wallets/get_wallet_credit"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/wallets/get_wallet_credit",
  "method": "GET",
  "headers": {
    "access_id": Your Access_id,
    "time": Time.now,
    "content-md5": Your Content-MD5,
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

This endpoint retrieves wallet credit.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/wallets/get_wallet_credit`



# User

## Get User Name

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/users/get_user_name")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/users/get_user_name"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/users/get_user_name"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/users/get_user_name",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": " first_name - last_name"
  }
]
```

This endpoint retrieves user's name.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/users/get_user_name`



## Get Favorite Authors For User

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/authors/favorite_authors")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/authors/favorite_authors"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/authors/favorite_authors"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/authors/favorite_authors",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "favorites": []
  }
]
```

This endpoint retrieves user's favorite authors.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/authors/favorite_authors`


# Order

## Get User's Orders

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "orders": [
      {
        "id": 36,
        "user_id": 50,
        "description": "",
        "price": 16.5,
        "author_id": null,
        "title": "First order",
        "state": "acceptable",
        "quality_level": 3,
        "processing_time": 3,
        "word_count_start": 25,
        "word_count_end": 50,
        "created_at": "2017-03-31T06:11:16.604Z",
        "updated_at": "2017-03-31T06:11:16.622Z",
        "category_id": 2,
        "seo_words": "camel",
        "valued_text": null,
        "status_comments": null,
        "ip_address": null,
        "want_title": false,
        "author_title": null
      }
    ]
  }
]
```

This endpoint retrieves user's orders.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders`


## Create an order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'
request["content-type"] = 'application/x-www-form-urlencoded'
request.body = "category=Your_category&description=Your_descriptin&title=Your_title&quality_level=Quality_level&processing_time=Days&word_count_start=Min_words&word_count_end=Max_words&seo_words=Comma separated words"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders"

payload = "category=Your_category&description=Your_descriptin&title=Your_title&quality_level=Quality_level&processing_time=Days&word_count_start=Min_words&word_count_end=Max_words&seo_words=Comma separated words"
headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    'content-type': "application/x-www-form-urlencoded",
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl -X POST -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" -H "Content-Type: application/x-www-form-urlencoded" -d 'category=industry&description=abc&title=test&quality_level=1&processing_time=7&word_count_start=25&word_count_end=50&seo_words=abc%2Cabc' "https://pronoun-io.herokuapp.com/api/v1/orders"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders",
  "method": "POST",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
    "content-type": "application/x-www-form-urlencoded",
  },
  "data": {
    "category": "industry",
    "description": "abc",
    "title": "test",
    "quality_level": "1",
    "processing_time": "7",
    "word_count_start": "25",
    "word_count_end": "50",
    "seo_words": "abc,abc"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "success": "Open Order created successfully."
  }
]
```

This endpoint retrieves user's orders.

### HTTP Request

`POST https://pronoun-io.herokuapp.com/api/v1/orders`

### Query Parameters

Parameter | Description
--------- | -----------
category | The category to which the order belongs
description | Description of the order
title | Title for the work
quality_level | Quality level of the author(2star,3star)
processing_time | Processing time in days
word_count_start | Minimum number of words
word_count_end | Maximum number of words
seo_words | SEO words

## Get state of an order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/get_state")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/get_state"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/get_state"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/33/get_state",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "state": "close"
  }
]
```

This endpoint retrieves status of the specified order.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/get_state`


### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question



## Get order cost

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/get_costs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/get_costs"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/get_costs"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/get_costs",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "rates_per_word": {
      "star_2": "0.22",
      "star_3": "0.33",
      "star_4": "0.44",
      "star_5": "0.55"
    }
  }
]
```

This endpoint retrieves rates per word for different quality authors.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/get_costs`



## Delete an order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/delete_order")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Delete.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'
request["content-type"] = 'application/x-www-form-urlencoded'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/delete_order"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    'content-type': "application/x-www-form-urlencoded"
    }

response = requests.request("DELETE", url, headers=headers)

print(response.text)
```

```shell
curl -X DELETE -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" -H "Content-Type: application/x-www-form-urlencoded" -d '' "https://pronoun-io.herokuapp.com/api/v1/orders/:id/delete_order"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/delete_order",
  "method": "DELETE",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
    "content-type": "application/x-www-form-urlencoded"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "order_id": 33
  }
]
```

This endpoint deletes the specified order.

### HTTP Request

`DELETE https://pronoun-io.herokuapp.com/api/v1/orders/:id/delete_order`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question



## Get Copyscape result

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/copyscape_result")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/copyscape_result"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/copyscape_result"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/copyscape_result",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "result": [
      "Minimum 15 words required."
    ]
  }
]
```

This endpoint retrieves copyscape results for the specified order.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/copyscape_result`


### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


## Preview Valued Text

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/text_preview")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/text_preview"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/text_preview"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/text_preview",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "state": "hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth "
  }
]
```

This endpoint retrieves text preview for the order.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/text_preview`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question



## Set SEO words

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/set_seo_words")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'
request["content-type"] = 'application/x-www-form-urlencoded'
request.body = "seo_words=Your_seo_words(comma seperated)"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/set_seo_words"

payload = "seo_words=Your_seo_words(comma seperated)"
headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    'content-type': "application/x-www-form-urlencoded"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl -X POST -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" -H "Content-Type: application/x-www-form-urlencoded" -d 'seo_words=Your_seo_words(comma seperated)' "https://pronoun-io.herokuapp.com/api/v1/orders/34/set_seo_words"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/set_seo_words",
  "method": "POST",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "seo_words": "Your_seo_words(comma seperated)"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "seo_words": "abc"
  }
]
```

This endpoint sets SEO words for the order.

### HTTP Request

`POST https://pronoun-io.herokuapp.com/api/v1/orders/:id/set_seo_words`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question

### Query Parameters

Parameter | Description
--------- | -----------
seo_words | Comma separated SEO tags



## Set Duration for an order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_duration")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'
request["content-type"] = 'application/x-www-form-urlencoded'
request.body = "processing_time=Processing_time_in_days"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_duration"

payload = "processing_time=Processing_time_in_days"
headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    'content-type': "application/x-www-form-urlencoded"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl -X POST -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" -H "Content-Type: application/x-www-form-urlencoded" -d 'processing_time=Processing_time_in_days' "https://pronoun-io.herokuapp.com/api/v1/orders/34/change_duration"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_duration",
  "method": "POST",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "processing_time": "Processing_time_in_days"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "duration": 9
  }
]
```

This endpoint sets SEO words for the order.

### HTTP Request

`POST https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_duration`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question

### Query Parameters

Parameter | Description
--------- | -----------
duration | The duration for completion of work in days



## Change word count

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_word_count")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'
request["content-type"] = 'application/x-www-form-urlencoded'
request.body = "word_count_start=Min_words&word_count_end=Max_words"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_word_count"

payload = "word_count_start=Min_words&word_count_end=Max_words"
headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    'content-type': "application/x-www-form-urlencoded"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl -X POST -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" -H "Content-Type: application/x-www-form-urlencoded" -d 'word_count_start=16&word_count_end=25' "https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_word_count"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_word_count",
  "method": "POST",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "word_count_start": "Min_words",
    "word_count_end": "Max_words"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "word_count": "16-25"
  }
]
```

This endpoint sets word limits for the order.

### HTTP Request

`POST https://pronoun-io.herokuapp.com/api/v1/orders/:id/change_word_count`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question

### Query Parameters

Parameter | Description
--------- | -----------
word_count_start | Minimum number of words
word_count_end | Maximum number of words



## Highlight Key Words

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/highlight_keywords")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/highlight_keywords"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/highlight_keywords"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/highlight_keywords",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    :highlighted_keywords=>"hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth "
  }
]
```

This endpoint retrieves highlighted keywords for the order.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/highlight_keywords`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


## Pick-up order(needs fixing)

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_order")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_order"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_order"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_order",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    :highlighted_keywords=>"hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth "
  }
]
```

This endpoint retrieves highlighted keywords for the order.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_order`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


## Pick-up multiple order(needs fixing)

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_multiple_orders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_multiple_orders"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_multiple_orders"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_multiple_orders",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "order_info": [
      {
        "id": 39,
        "price": 11,
        "author_id": null,
        "processing_time": 7,
        "valued_text": null
      },
      {
        "id": 42,
        "price": 11,
        "author_id": null,
        "processing_time": 7,
        "valued_text": "this is my text and this is to test the pickup order thing i iiiii :P"
      }
    ]
  }
]
```

This endpoint picksup all the orders of the user.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/pickup_multiple_orders`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


## Accept An Order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/accept_order")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/accept_order"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/accept_order"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/accept_order",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "order_info": {
      "id": 34,
      "price": 55,
      "author_id": 19,
      "processing_time": 9,
      "valued_text": "hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth "
    }
  }
]
```

This endpoint changes the state of the order to accepted.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/accept_order`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


## Reject An Order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/reject_order")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/reject_order"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/reject_order"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/reject_order",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "order_info": {
      "id": 34,
      "price": 55,
      "author_id": 19,
      "processing_time": 9,
      "valued_text": "hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth "
    }
  }
]
```

This endpoint changes the state of the order to rejected.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/reject_order`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


## Revise An Order

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/orders/:id/revise_order")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/orders/:id/revise_order"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/orders/:id/revise_order"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/orders/:id/revise_order",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "order_info": {
      "id": 34,
      "price": 55,
      "author_id": 19,
      "processing_time": 9,
      "valued_text": "hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth hello Paul really likes pickles in his mouth Paul also puts a little lumpy fudge in his mouth "
    }
  }
]
```

This endpoint changes the state of the order to revision.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/orders/:id/revise_order`

### URL Parameters

Parameter | Description
--------- | -----------
:id | The ID of the order in question


# Categories

## Get All Categories

```ruby
require 'uri'
require 'net/http'

url = URI("https://pronoun-io.herokuapp.com/api/v1/categories")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["access_id"] = '7493ffbeb7a8d221f6d15987945d8228'
request["time"] = '2017'
request["content-md5"] = '64b4aa1d9e883e0e18a920dabf8f50db'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://pronoun-io.herokuapp.com/api/v1/categories"

headers = {
    'access_id': "7493ffbeb7a8d221f6d15987945d8228",
    'time': "2017",
    'content-md5': "64b4aa1d9e883e0e18a920dabf8f50db",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "ACCESS_ID: 7493ffbeb7a8d221f6d15987945d8228" -H "Time: 2017" -H "CONTENT-MD5: 64b4aa1d9e883e0e18a920dabf8f50db" "https://pronoun-io.herokuapp.com/api/v1/categories"
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://pronoun-io.herokuapp.com/api/v1/categories",
  "method": "GET",
  "headers": {
    "access_id": "7493ffbeb7a8d221f6d15987945d8228",
    "time": "2017",
    "content-md5": "64b4aa1d9e883e0e18a920dabf8f50db",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "categories": [
      {
        "id": 1,
        "name": "industry",
        "created_at": "2016-12-01T14:50:14.237Z",
        "updated_at": "2016-12-01T14:50:14.237Z"
      },
      {
        "id": 2,
        "name": "animals",
        "created_at": "2016-12-02T13:03:22.907Z",
        "updated_at": "2016-12-02T13:03:22.907Z"
      },
      {
        "id": 3,
        "name": "arts and crafts",
        "created_at": "2016-12-02T13:03:22.935Z",
        "updated_at": "2016-12-02T13:03:22.935Z"
      }
    ]
  }
]
```

This endpoint retrieves All Categories.

### HTTP Request

`GET https://pronoun-io.herokuapp.com/api/v1/categories`
