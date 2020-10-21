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
var settings = {
  "method": "GET",
  "timeout": 0,
  "headers": {
    "Api-key": "Your_API_Key",
    "Accept": "application/json",
  },
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> Make sure to replace `Your_API_Key` with your API key.

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
        "https://circular-hawk-253618.appspot.com/companyInfoFull/, 
        headers=headers).json()
```


```javascript
var settings = {
  "url": "https://circular-hawk-253618.appspot.com/companyInfoFull/",
  "method": "GET",
  "timeout": 0,
  "headers": {
    "Api-key": "Your_API_Key",
    "Accept": "application/json",
  },
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
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
[
  {  '_1_1_1_AirQuality_List': None,
     '_1_1_2_ComplianceEnvironmentalRegulations_List': None,
     '_1_1_3_EnergyMgmt_List': None,
     '_1_1_4_FuelMgmt_List': None,
     '_1_1_5_GHGemissions_List': None,
     '_1_2_1_EnvironmentalImpactsAssetsOperations_List': None,
     '_1_2_2_SupplierEnvironmentalAssessment_List': None,
     '_1_2_3_EnvironBusinessDevelopment_List': None,
     '_1_2_4_EvaluationEnvironKPI_List': None,
     '_1_2_5_LifecycleImpactsProductsServices_List': None,
     '_1_2_6_ProductPackaging_List': None,
     '_1_2_7_ProductQualitySafety_List': 45.6438,
     '_1_2_8_ResponsibleConsumptionProduction_List': None,
     '_1_3_1_BiodiversityImpacts_List': None,
     '_1_3_2_WaterWastewaterMgmt_List': None,
     '_1_3_3_WasteHazardousMaterialsMgmt_List': None,
     '_2_1_1_HealthSafety_List': 9.5,
     '_2_2_1_FairLaborPractices_List': 39.4787,
     '_2_2_2_LaborMgmtRelations_List': 36.6572,
     '_2_2_3_TrainingEducation_List': 40.2849,
     '_2_2_4_DiversityEqualOpportunity_List': 39.8905,
     '_2_2_5_CompensationBenefits_List': 36.4794,
     '_2_2_6_RecruitmentDevelopmentRetention_List': 40.0974,
     '_2_3_1_AccessAffordability_List': None,
     '_2_3_2_CustomerHealthSafety_List': None,
     '_2_3_3_CustomerPrivacy_List': None,
     '_2_3_4_FairDisclosureLabeling_List': None,
     '_2_3_5_FairMarketingAdvertising_List': None,
     '_2_3_6_LocalCommunities_List': 37.046,
     '_2_3_7_SocialImpactsAssetsOperations_List': 43.4955,
     '_2_4_1_ChildLabor_List': 27.98,
     '_2_4_2_FreedomAssociationCollectiveBargaining_List': 16.9933,
     '_2_4_3_HumanRights_List': 29.9267,
     '_2_4_4_NonDiscrimination_List': 39.4199,
     '_2_4_5_RightsIndigenousPeoples_List': 15.3267,
     '_3_1_1_BoardLeadership_List': 39.8389,
     '_3_1_2_CeoExecutiveLeadership_List': 40.2633,
     '_3_1_3_ManagementLeadership_List': 40.1722,
     '_3_1_4_InternalControlRisks_List': 37.0,
     '_3_2_1_EconomicPerformance_List': 37.6667,
     '_3_2_2_IndustryInnovationInfrastructure_List': 34.3333,
     '_3_2_3_MarketPresence_List': 38.3333,
     '_3_3_1_IndirectEconomicImpacts_List': 38.3333,
     '_3_3_2_Partnerships_List': 9.0,
     '_3_3_3_PeaceJusticeInstitutions_List': None,
     '_3_3_4_Transparency_List': None,
     '_3_4_1_AntiCorruptionPolicies_List': None,
     '_3_4_2_AntiCompetitiveBehavior_List': None,
     '_3_4_3_BusinessEthicsTransparencyPayments_List': None,
     '_3_4_4_RegulatoryCapturePoliticalInfluence_List': 44.3051,
     'company_idx': 1,
     'criticalCountries_List': 0,
     'noAccountingControv_List': 0,
     'noAntiCompetition_List': 0,
     'noBusinessEthics_List': 0,
     'noChildLabor_List': 0,
     'noEnvironmentControv_List': 0,
     'noHumanRights_List': 0,
     'noIPcontrov_List': 0,
     'noInsiderTrading_List': 0,
     'noMgmtCompensation_List': 0,
     'noMgmtDepartures_List': 0,
     'noPrivacyControv_List': 0,
     'noResponsibleMarketing_List': 0,
     'noTax_List': 0,
     'noWorkingCondition_List': 1,
     'nocustomerHealthSafety_List': 0,
     'provider': 'Shacknews',
     'relevancy10_List': 0.0,
     'relevancy11_List': 0.0,
     'relevancy12_List': 0.08,
     'relevancy13_List': 0.0,
     'relevancy14_List': 0.0,
     'relevancy15_List': 0.0,
     'relevancy16_List': 0.0,
     'relevancy17_List': 0.0,
     'relevancy18_List': 0.12,
     'relevancy19_List': 0.07,
     'relevancy1_List': 0.0,
     'relevancy20_List': 0.11,
     'relevancy21_List': 0.12,
     'relevancy22_List': 0.0,
     'relevancy23_List': 0.11,
     'relevancy24_List': 0.0,
     'relevancy25_List': 0.0,
     'relevancy26_List': 0.0,
     'relevancy27_List': 0.0,
     'relevancy28_List': 0.0,
     'relevancy29_List': 0.08,
     'relevancy2_List': 0.0,
     'relevancy30_List': 0.11,
     'relevancy31_List': 0.0,
     'relevancy32_List': 0.0,
     'relevancy33_List': 0.0,
     'relevancy34_List': 0.12,
     'relevancy35_List': 0.0,
     'relevancy36_List': 0.0,
     'relevancy37_List': 0.0,
     'relevancy38_List': 0.0,
     'relevancy39_List': 0.0,
     'relevancy3_List': 0.0,
     'relevancy40_List': 0.0,
     'relevancy41_List': 0.0,
     'relevancy42_List': 0.0,
     'relevancy43_List': 0.0,
     'relevancy44_List': 0.0,
     'relevancy45_List': 0.0,
     'relevancy46_List': 0.0,
     'relevancy47_List': 0.0,
     'relevancy48_List': 0.0,
     'relevancy49_List': 0.0,
     'relevancy4_List': 0.0,
     'relevancy50_List': 0.08,
     'relevancy5_List': 0.0,
     'relevancy6_List': 0.0,
     'relevancy7_List': 0.0,
     'relevancy8_List': 0.0,
     'relevancy9_List': 0.0,
     'relevancy_List': 75.0,
     'summary': '... power to cancel contracts with firms found to be organizing training \nrelated to racial diversity, sexual identity, or gender identity. In its \nstatement, Microsoft said:.',
     'timestamp': '2020-10-07 00:00:00',
     'title': 'Microsoft responds to Labor Department probe over diversity policy',
     'topics': '30,18,21,34,20,23,50,12,29,19,22,36,38,33,37,32,35,39,40,41,42,43,',
     'url': 'https://www.shacknews.com/article/120774/microsoft-responds-to-labor-department-probe-over-diversity-policy',
     'words': '490,604,79,323,75,356,383,173,338,430,331,21,170,281,582,249,,'
 },
 [...]
]
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






