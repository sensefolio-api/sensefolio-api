---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - python
  - javascript

toc_footers:
  - <a href='https://sensefolio.com/'>Sign Up for a Sensefolio API Key</a>
  - 
  - <a href='#'>ESG Data Powered by Sensefolio</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Sensefolio API Documentation

**Welcome to the Sensefolio API !**

You can use our API to access Sensefolio API endpoints, which can get Sensefolio ESG Data.<br>
Any questions on the Sensefolio ESG Data? Please contact us: <contact@sensefolio.com> or visit <a href='https://sensefolio.com/'>sensefolio.com</a>

We have language bindings in Python and JavaScript! 

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

To request an API Key, please contact <contact@sensefolio.com> or visit <a href='https://sensefolio.com/'>sensefolio.com</a>

# Authentication

> To authorize, use this code:

```python
import requests

apiKey = 'Your_API_Key'

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Sensefolio uses API keys to allow access to the API. 
To request an API Key, please contact <contact@sensefolio.com> or visit <a href='https://sensefolio.com/'>sensefolio.com</a>

Sensefolio expects for the API key to be included in all API requests to the server in a header that looks like the following:

`apiKey: YOUR_API_KEY`

**Security Warning:**
It's important to secure your API Key against public access. The custom header option is strongly recommended over the querystring option for passing your API Key in a production environment.

**Standards and Conventions**
Each HTTP request must contain the header Accept: application/json.

**Errors and Rate Limits**
API Request Throttling
Use of the Sensefolio API is subject to API call rate limiting or "request throttling". This is the number of HTTP calls that can be made simultaneously or within the same minute with your API Key before receiving an HTTP 429 "Too Many Requests" throttling error.

<aside class="notice">
Note: Making HTTP requests on the client side with Javascript is currently prohibited through CORS configuration. This is to protect your API Key which should not be visible to users of your application, so your API Key is not stolen. Secure your API Key by routing calls through your own backend service..
</aside>



# Get Full List of Companies

## Get All Companies covered by Sensefolio (whether they Public or Private)

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/companyInfoFull?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/companyInfoFull`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.






# Company ESG Score

## Get All ESG Scores for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/companyScore?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/companyScore`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All ESG Scores for a Specific Company for a Specific Period

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/companyScore?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/companyScore`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve




# Get Most Recent Company ESG Score

## Get Most Recent Company ESG Score

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/companyLastScore?
        company_idx="+str(company_idx)"
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/companyLastScore`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
company_idx | none | It is necessary to include a "company_idx".





# Get Scores for a Specific Peer Group

## Get Scores for a Specific Peer Group

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/peerGroupScore?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/peerGroupScore`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.







# News

## Get All News for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualNews3`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.
**1.1 AIR QUALITY**<br>
'air_quality'<br>
'environment_compliance'<br>
'energy_mgmt'<br>
'fuel_mgmt'<br>
'ghg_emissions'<br>

**1.2 SUSTAINABILITY**<br>
'environmental_impact'<br>
'supplier_environment'<br>
'environment_business_dev'<br>
'environment_kpi'<br>
'lifecycle_impacts'<br>
'product_packaging'<br>
'product_quality_safety'<br>
'responsible_consumption_prod'<br>

**1.3 BIODIVERSITY AND WATER**<br>
'biodiv_impacts'<br>
'water_mgmt'<br>
'waste_mgmt'<br>

**2.1 HEALTH & SAFETY**<br>
'health_safety'<br>
    
**2.2 EMPLOYEE STANDARDS**<br>
'fair_labor'<br>
'labor_mgmt_relations'<br>
'training_education'<br>
'diversity_equal'<br>
'compensation_benefits'<br>
'recruitment_dev'<br>

**2.3 COMMUNITY RESPONSIBILITY**<br>
'access_affordability'<br>
'customer_health'<br>
'customer_privacy'<br>
'fair_disclosure'<br>
'fair_marketing'<br>
'local_communities'<br>
'social_impacts'<br>

**2.4 HUMAN RIGHTS**<br>
'child_labor'<br>
'freedom_association'<br>
'human_rights'<br>
'non_discrimination'<br>
'rights_indigenous'<br>

**3.1 LEADERSHIP/MGMT STRUCTURE**<br>
'board_leadership'<br>
'ceo_exec_leadership'<br>
'management_leadership'<br>
'internal_control'<br>

**3.2 BUSINESS INNOVATION AND PERFORMANCE**<br>
'economic_perf'<br>
'industry_innovation'<br>
'market_presence'<br>

**3.3. OUTSIDE ACTIVITIES**<br>
'indirect_impacts'<br>
'partnerships'<br>
'peace_justice'<br>
'transparency'<br>

**3.4. BUSINESS ETHICS**<br>
'anti_corruption'<br>
'anti_competitive'<br>
'business_ethics_transparency'<br>
'regulatory_capture'<br>

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All News for a Specific Company for a Specific Topic

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualNews3`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve




# Tweets

## Get All Tweets for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualTweets?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualTweets`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All Tweets for a Specific Company for a Specific Topic

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualTweets?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualTweets`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve





# G Company Reviews

## Get All G Company Reviews for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualGlassdoor?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualGlassdoor`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All G Company Reviews for a Specific Company for a Specific Topic

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualGlassdoor?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualGlassdoor`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve





# I Company Reviews

## Get All I Company Reviews for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualIndeed?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualIndeed`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All I Company Reviews for a Specific Company for a Specific Topic

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualIndeed?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualIndeed`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve







# Carbon Disclosure

## Get All Carbon Disclosure Information for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualCDP?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualCDP`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All Carbon Disclosure Information for a Specific Company for a Specific Topic

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualCDP?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualCDP`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve









# Violation Tracker

## Get All Violation Information for a Specific Company

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualViolationTracker?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves all news.

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualViolationTracker`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All Violation Information for a Specific Company for a Specific Topic

```python
import requests

apiKey = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics"

headers = {'x-api-key': apiKey,
           'content-type': 'application/json'}

companyScore_companyExample_ActualNews = requests.get(
        "https://circular-hawk-253618.appspot.com/ActualViolationTracker?
        company_idx="+str(company_idx)+"&
        start_date=str(start_date)&
        end_date=str(end_date)&
        category=&
        topic=str(topic)&
        criteria=&
        word="
        , headers=headers).json()
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

This endpoint retrieves a news for a specific company and for a specific Sensefolio topic.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://circular-hawk-253618.appspot.com/ActualViolationTracker`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve






