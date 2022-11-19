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

API_KEY = 'Your_API_Key'

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}
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

`API_KEY: YOUR_API_KEY`

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

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

companyInfoFull = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/companyInfoFull/, 
        headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/companyInfoFull/",
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
  'BLOOMBERG_id': 'AAPL US',
  'CUSIP': '37833100',
  'Company_Website': 'https://www.apple.com/',
  'Company_idx': '0',
  'Controversy': '[]',
  'Exchange_Country_Region': 'North America',
  'FE_Country': 'United States of America',
  'FE_Factsetid': '3783310',
  'Fun_Fact': "Did you know: Apple Inc. is the world's largest information technology company by revenue. wikipedia.org",
  'GICS_Industry_Name': 'Technology Hardware & Equipmen',
  'GICS_Sector_Name': 'Information Technology',
  'Google_Ticker': 'AAPL ',
  'ISIN': 'US0378331005',
  'Name': 'Apple Inc.',
  'SEDOL': '2046251',
  'Short_Description': 'Apple Inc. is an American multinational technology company headquartered in Cupertino, California, that designs, develops, and sells consumer electronics, computer software, and online services. It is considered one of the Big Four of technology along with Amazon, Google, and Facebook.',
  'Subsidiaries': 'Subsidiaries: Beats Electronics, Apple Store, FileMaker, Beddit, MORE',
  'Symbol': 'AAPL',
  'yahooTickers': "[('Apple Inc.', 'AAPL', 'NMS', 'NASDAQ'), ('ICE Leveraged 2x AAPL Index', '^NY2LAAPL', 'NYS', 'NYSE'), ('Apple Inc.', 'AAPL.BA', 'YHD', 'Industry'), ('Apple Inc.', 'AAPL34.SA', 'SAO', 'Sao Paolo'), ('Apple Inc.', 'AAPL.MX', 'MEX', 'Mexico'), ('APPLE', 'AAPL.MI', 'MIL', 'Milan'), ('APPLE INC', 'AAPLD.BA', 'BUE', 'Buenos Aires'), ('APPLE INC', 'AAPLC.BA', 'BUE', 'Buenos Aires'), ('Apple Inc.', 'AAPL.VI', 'VIE', 'Vienna')]"
  },
  
  {'BLOOMBERG_id': 'MSFT US',
  'CUSIP': '594918104',
  'Company_Website': 'https://www.microsoft.com/en-us/',
  'Company_idx': '1',
  'Controversy': '[]',
  'Exchange_Country_Region': 'North America',
  'FE_Country': 'United States of America',
  'FE_Factsetid': '59491810',
  'Fun_Fact': "Did you know: Microsoft is the world's sixth-largest information technology company by revenue. wikipedia.org",
  'GICS_Industry_Name': 'Software & Services',
  'GICS_Sector_Name': 'Information Technology',
  'Google_Ticker': 'MSFT',
  'ISIN': 'US5949181045',
  'Name': 'Microsoft Corporation',
  'SEDOL': '2588173',
  'Short_Description': 'Microsoft Corporation is an American multinational technology company with headquarters in Redmond, Washington. It develops, manufactures, licenses, supports and sells computer software, consumer electronics, personal computers, and related services.',
  'Subsidiaries': None,
  'Symbol': 'MSFT',
  'yahooTickers': "[('Microsoft Corporation', 'MSFT', 'NAS', 'NASDAQ'), ('Microsoft Corporation', 'MSFT.BA', 'BUE', 'Buenos Aires'), ('Microsoft Corporation', 'MSF.DE', 'FRA', 'Frankfurt'), ('Microsoft Corporation', 'MSFT.MX', 'YHD', 'Industry'), ('Microsoft Corporation', 'MSF.F', 'FRA', 'Frankfurt'), ('Microsoft Corporation', 'MSFT34.SA', 'YHD', 'Industry'), ('MICROSOFT  DL-,00000625', 'MSF.MU', 'MUN', 'Munich'), ('Microsoft Corporation', 'MSFT.VI', 'VIE', 'Vienna'), ('Leverage Shares 2x Microsoft ETC A', 'MSF2.L', 'LSE', 'London')]"
  }
  ,
  [...]
]
```

This endpoint retrieves all details about companies covered by Sensefolio.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/companyInfoFull`




# Company ESG Score

## Get All ESG Scores for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

companyScore = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/companyScore?
        company_idx="+str(company_idx)+"&
        start_date=&
        end_date="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/companyScore?
        company_idx="+str(company_idx)",
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
 'ESG_Score': 51.2446,
 'E_Score': 63.7461,
 'G_Score': 37.4518,
 'S_Score': 48.3687,
 '_1_1_1_AirQuality_List': 65.1078,
 '_1_1_2_ComplianceEnvironmentalRegulations_List': 64.538,
 '_1_1_3_EnergyMgmt_List': 55.824,
 '_1_1_4_FuelMgmt_List': 64.3942,
 '_1_1_5_GHGemissions_List': 69.6143,
 '_1_2_1_EnvironmentalImpactsAssetsOperations_List': 71.4676,
 '_1_2_2_SupplierEnvironmentalAssessment_List': 70.0738,
 '_1_2_3_EnvironBusinessDevelopment_List': 60.8153,
 '_1_2_4_EvaluationEnvironKPI_List': 59.6665,
 '_1_2_5_LifecycleImpactsProductsServices_List': 68.8307,
 '_1_2_6_ProductPackaging_List': 62.153,
 '_1_2_7_ProductQualitySafety_List': 55.4965,
 '_1_2_8_ResponsibleConsumptionProduction_List': 67.3626,
 '_1_3_1_BiodiversityImpacts_List': 63.6938,
 '_1_3_2_WaterWastewaterMgmt_List': 63.0612,
 '_1_3_3_WasteHazardousMaterialsMgmt_List': 57.8377,
 '_2_1_1_HealthSafety_List': 48.9008,
 '_2_2_1_FairLaborPractices_List': 47.62,
 '_2_2_2_LaborMgmtRelations_List': 49.7854,
 '_2_2_3_TrainingEducation_List': 47.9361,
 '_2_2_4_DiversityEqualOpportunity_List': 43.2989,
 '_2_2_5_CompensationBenefits_List': 58.9116,
 '_2_2_6_RecruitmentDevelopmentRetention_List': 47.4877,
 '_2_3_1_AccessAffordability_List': 50.0944,
 '_2_3_2_CustomerHealthSafety_List': 44.6985,
 '_2_3_3_CustomerPrivacy_List': 56.2303,
 '_2_3_4_FairDisclosureLabeling_List': 42.561,
 '_2_3_5_FairMarketingAdvertising_List': 45.4074,
 '_2_3_6_LocalCommunities_List': 43.9781,
 '_2_3_7_SocialImpactsAssetsOperations_List': 47.5677,
 '_2_4_1_ChildLabor_List': 51.9795,
 '_2_4_2_FreedomAssociationCollectiveBargaining_List': 44.0635,
 '_2_4_3_HumanRights_List': 50.0202,
 '_2_4_4_NonDiscrimination_List': 53.6658,
 '_2_4_5_RightsIndigenousPeoples_List': 44.7986,
 '_3_1_1_BoardLeadership_List': 34.8689,
 '_3_1_2_CeoExecutiveLeadership_List': 41.1944,
 '_3_1_3_ManagementLeadership_List': 40.2077,
 '_3_1_4_InternalControlRisks_List': 45.2186,
 '_3_2_1_EconomicPerformance_List': 48.5752,
 '_3_2_2_IndustryInnovationInfrastructure_List': 39.442,
 '_3_2_3_MarketPresence_List': 37.9337,
 '_3_3_1_IndirectEconomicImpacts_List': 28.0025,
 '_3_3_2_Partnerships_List': 33.2155,
 '_3_3_3_PeaceJusticeInstitutions_List': 44.1231,
 '_3_3_4_Transparency_List': 24.7201,
 '_3_4_1_AntiCorruptionPolicies_List': 29.7044,
 '_3_4_2_AntiCompetitiveBehavior_List': 35.1254,
 '_3_4_3_BusinessEthicsTransparencyPayments_List': 33.5263,
 '_3_4_4_RegulatoryCapturePoliticalInfluence_List': 45.9191,
 'company_idx': 1,
 'company_symbol': 'MSFT',
 'timestamp': '2020-07-16 00:00:00'
 },
 [...]
]
```

This endpoint retrieves all ESG Scores for a Specific Company.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/companyScore`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | No |Start Date using the "YYYY-MM-DD" format
end_date | None | No |End Date using the "YYYY-MM-DD" format

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All ESG Scores for a Specific Company for a Specific Period

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

companyScore = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/companyScore?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/companyScore?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)",
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


This endpoint retrieves ESG Scores for a specific company.


### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/companyScore`

### URL Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | No |Start Date using the "YYYY-MM-DD" format
end_date | None | No |End Date using the "YYYY-MM-DD" format




# Get Most Recent Company ESG Score

## Get Most Recent Company ESG Score

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

companyLastScore = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/companyLastScore?
        company_idx="+str(company_idx)
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/companyLastScore?
        company_idx="+str(company_idx)",
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
      'ESG_Score': 50.7731,
      'E_Score': 63.9811,
      'G_Score': 36.0265,
      'S_Score': 47.9091,
      '_1_1_1_AirQuality_List': 64.4268,
      '_1_1_2_ComplianceEnvironmentalRegulations_List': 63.8583,
      '_1_1_3_EnergyMgmt_List': 56.037,
      '_1_1_4_FuelMgmt_List': 63.451,
      '_1_1_5_GHGemissions_List': 71.3891,
      '_1_2_1_EnvironmentalImpactsAssetsOperations_List': 72.053,
      '_1_2_2_SupplierEnvironmentalAssessment_List': 71.2368,
      '_1_2_3_EnvironBusinessDevelopment_List': 61.0821,
      '_1_2_4_EvaluationEnvironKPI_List': 60.2519,
      '_1_2_5_LifecycleImpactsProductsServices_List': 69.4161,
      '_1_2_6_ProductPackaging_List': 62.7384,
      '_1_2_7_ProductQualitySafety_List': 55.6888,
      '_1_2_8_ResponsibleConsumptionProduction_List': 67.9481,
      '_1_3_1_BiodiversityImpacts_List': 62.987,
      '_1_3_2_WaterWastewaterMgmt_List': 63.3717,
      '_1_3_3_WasteHazardousMaterialsMgmt_List': 57.7619,
      '_2_1_1_HealthSafety_List': 49.8627,
      '_2_2_1_FairLaborPractices_List': 46.7003,
      '_2_2_2_LaborMgmtRelations_List': 49.7943,
      '_2_2_3_TrainingEducation_List': 48.1099,
      '_2_2_4_DiversityEqualOpportunity_List': 41.6872,
      '_2_2_5_CompensationBenefits_List': 59.8534,
      '_2_2_6_RecruitmentDevelopmentRetention_List': 47.722,
      '_2_3_1_AccessAffordability_List': 50.244,
      '_2_3_2_CustomerHealthSafety_List': 43.8448,
      '_2_3_3_CustomerPrivacy_List': 55.4821,
      '_2_3_4_FairDisclosureLabeling_List': 40.5094,
      '_2_3_5_FairMarketingAdvertising_List': 42.0746,
      '_2_3_6_LocalCommunities_List': 43.403,
      '_2_3_7_SocialImpactsAssetsOperations_List': 46.2927,
      '_2_4_1_ChildLabor_List': 51.0914,
      '_2_4_2_FreedomAssociationCollectiveBargaining_List': 44.6712,
      '_2_4_3_HumanRights_List': 50.6278,
      '_2_4_4_NonDiscrimination_List': 51.4645,
      '_2_4_5_RightsIndigenousPeoples_List': 46.8372,
      '_3_1_1_BoardLeadership_List': 32.7329,
      '_3_1_2_CeoExecutiveLeadership_List': 40.5428,
      '_3_1_3_ManagementLeadership_List': 38.8016,
      '_3_1_4_InternalControlRisks_List': 46.6014,
      '_3_2_1_EconomicPerformance_List': 49.0381,
      '_3_2_2_IndustryInnovationInfrastructure_List': 40.2201,
      '_3_2_3_MarketPresence_List': 39.2967,
      '_3_3_1_IndirectEconomicImpacts_List': 21.0385,
      '_3_3_2_Partnerships_List': 32.4403,
      '_3_3_3_PeaceJusticeInstitutions_List': 41.4369,
      '_3_3_4_Transparency_List': 22.3983,
      '_3_4_1_AntiCorruptionPolicies_List': 30.3631,
      '_3_4_2_AntiCompetitiveBehavior_List': 32.2275,
      '_3_4_3_BusinessEthicsTransparencyPayments_List': 30.8651,
      '_3_4_4_RegulatoryCapturePoliticalInfluence_List': 42.3947,
      'company_idx': 1,
      'company_symbol': 'MSFT',
      'timestamp': '21/10/2020 21:09:16'
  }
]
```

This endpoint retrieves the most recent ESG Scores for a specified Company.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/companyLastScore`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
company_idx | none | It is necessary to include a "company_idx".





# Get Scores for a Specific Peer Group

## Get Scores for a Specific Peer Group

```python
import requests

API_KEY = 'Your_API_Key'
unique_peer_group_ID = 64
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

peerGroupScore = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/peerGroupScore?
        unique_peer_group_ID="+str(unique_peer_group_ID)+"&
        start_date="+str(start_date)&
        end_date="+str(end_date)
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/peerGroupScore?
        unique_peer_group_ID="+str(unique_peer_group_ID)+"&
        start_date="+str(start_date)&
        end_date="+str(end_date),
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
     'ESG_Score': 48.8348,
     'E_Score': 48.153,
     'G_Score': 53.3381,
     'S_Score': 45.2407,
     '_1_1_1_AirQuality_List': 44.7844,
     '_1_1_2_ComplianceEnvironmentalRegulations_List': 48.1099,
     '_1_1_3_EnergyMgmt_List': 55.5799,
     '_1_1_4_FuelMgmt_List': 42.3383,
     '_1_1_5_GHGemissions_List': 60.0476,
     '_1_2_1_EnvironmentalImpactsAssetsOperations_List': 50.1574,
     '_1_2_2_SupplierEnvironmentalAssessment_List': 44.6447,
     '_1_2_3_EnvironBusinessDevelopment_List': 54.6199,
     '_1_2_4_EvaluationEnvironKPI_List': 50.9873,
     '_1_2_5_LifecycleImpactsProductsServices_List': 28.3367,
     '_1_2_6_ProductPackaging_List': 43.89,
     '_1_2_7_ProductQualitySafety_List': 69.6385,
     '_1_2_8_ResponsibleConsumptionProduction_List': 41.9671,
     '_1_3_1_BiodiversityImpacts_List': 34.9827,
     '_1_3_2_WaterWastewaterMgmt_List': 40.8195,
     '_1_3_3_WasteHazardousMaterialsMgmt_List': 59.5435,
     '_2_1_1_HealthSafety_List': 54.109,
     '_2_2_1_FairLaborPractices_List': 39.0988,
     '_2_2_2_LaborMgmtRelations_List': 54.5424,
     '_2_2_3_TrainingEducation_List': 35.6605,
     '_2_2_4_DiversityEqualOpportunity_List': 30.8102,
     '_2_2_5_CompensationBenefits_List': 44.0497,
     '_2_2_6_RecruitmentDevelopmentRetention_List': 26.1366,
     '_2_3_1_AccessAffordability_List': 56.3433,
     '_2_3_2_CustomerHealthSafety_List': 37.028,
     '_2_3_3_CustomerPrivacy_List': 53.9968,
     '_2_3_4_FairDisclosureLabeling_List': 45.2836,
     '_2_3_5_FairMarketingAdvertising_List': 53.6808,
     '_2_3_6_LocalCommunities_List': 58.7759,
     '_2_3_7_SocialImpactsAssetsOperations_List': 57.5379,
     '_2_4_1_ChildLabor_List': 38.8744,
     '_2_4_2_FreedomAssociationCollectiveBargaining_List': 35.6982,
     '_2_4_3_HumanRights_List': 52.2012,
     '_2_4_4_NonDiscrimination_List': 30.7325,
     '_2_4_5_RightsIndigenousPeoples_List': 55.0131,
     '_3_1_1_BoardLeadership_List': 56.4643,
     '_3_1_2_CeoExecutiveLeadership_List': 68.7967,
     '_3_1_3_ManagementLeadership_List': 53.0035,
     '_3_1_4_InternalControlRisks_List': 44.138,
     '_3_2_1_EconomicPerformance_List': 38.9295,
     '_3_2_2_IndustryInnovationInfrastructure_List': 58.2354,
     '_3_2_3_MarketPresence_List': 50.9226,
     '_3_3_1_IndirectEconomicImpacts_List': 60.7084,
     '_3_3_2_Partnerships_List': 54.1638,
     '_3_3_3_PeaceJusticeInstitutions_List': 39.1283,
     '_3_3_4_Transparency_List': 45.2281,
     '_3_4_1_AntiCorruptionPolicies_List': 69.8086,
     '_3_4_2_AntiCompetitiveBehavior_List': 43.7878,
     '_3_4_3_BusinessEthicsTransparencyPayments_List': 57.7795,
     '_3_4_4_RegulatoryCapturePoliticalInfluence_List': 58.9771,
     'peer_group': 'East Europe - Real Estate',
     'timestamp': '2020-01-01 00:00:00',
     'unique_peer_group_ID': 64
 },
 [...]
]
```

This endpoint retrieves all ESG Scores for a Specific Peer Group (ie. Region/Industry).

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/peerGroupScore`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
unique_peer_group_ID | None | No | The IDX assigned by Sensefolio for a Peer Group
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format






# News

## Get All News for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualNews = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)"+&
        end_date="+str(end_date)"+&
        category=&
        topic=&
        criteria=&
        word=&
        controv="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)"+&
        end_date="+str(end_date)"+&
        category=&
        topic=&
        criteria=&
        word=&
        controv=",
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
     '_1_1_1_AirQuality_List': None,
     '_1_1_2_ComplianceEnvironmentalRegulations_List': None,
     '_1_1_3_EnergyMgmt_List': None,
     '_1_1_4_FuelMgmt_List': None,
     '_1_1_5_GHGemissions_List': None,
     '_1_2_1_EnvironmentalImpactsAssetsOperations_List': None,
     '_1_2_2_SupplierEnvironmentalAssessment_List': 89.2875,
     '_1_2_3_EnvironBusinessDevelopment_List': None,
     '_1_2_4_EvaluationEnvironKPI_List': None,
     '_1_2_5_LifecycleImpactsProductsServices_List': None,
     '_1_2_6_ProductPackaging_List': None,
     '_1_2_7_ProductQualitySafety_List': 85.3587,
     '_1_2_8_ResponsibleConsumptionProduction_List': None,
     '_1_3_1_BiodiversityImpacts_List': None,
     '_1_3_2_WaterWastewaterMgmt_List': 73.5725,
     '_1_3_3_WasteHazardousMaterialsMgmt_List': None,
     '_2_1_1_HealthSafety_List': None,
     '_2_2_1_FairLaborPractices_List': None,
     '_2_2_2_LaborMgmtRelations_List': None,
     '_2_2_3_TrainingEducation_List': None,
     '_2_2_4_DiversityEqualOpportunity_List': None,
     '_2_2_5_CompensationBenefits_List': None,
     '_2_2_6_RecruitmentDevelopmentRetention_List': None,
     '_2_3_1_AccessAffordability_List': None,
     '_2_3_2_CustomerHealthSafety_List': None,
     '_2_3_3_CustomerPrivacy_List': None,
     '_2_3_4_FairDisclosureLabeling_List': None,
     '_2_3_5_FairMarketingAdvertising_List': None,
     '_2_3_6_LocalCommunities_List': None,
     '_2_3_7_SocialImpactsAssetsOperations_List': None,
     '_2_4_1_ChildLabor_List': None,
     '_2_4_2_FreedomAssociationCollectiveBargaining_List': None,
     '_2_4_3_HumanRights_List': None,
     '_2_4_4_NonDiscrimination_List': None,
     '_2_4_5_RightsIndigenousPeoples_List': None,
     '_3_1_1_BoardLeadership_List': 81.2392,
     '_3_1_2_CeoExecutiveLeadership_List': 81.9058,
     '_3_1_3_ManagementLeadership_List': 82.2392,
     '_3_1_4_InternalControlRisks_List': 81.4058,
     '_3_2_1_EconomicPerformance_List': 86.487,
     '_3_2_2_IndustryInnovationInfrastructure_List': 84.7971,
     '_3_2_3_MarketPresence_List': 84.9058,
     '_3_3_1_IndirectEconomicImpacts_List': 86.287,
     '_3_3_2_Partnerships_List': 82.887,
     '_3_3_3_PeaceJusticeInstitutions_List': 85.3587,
     '_3_3_4_Transparency_List': 85.3587,
     '_3_4_1_AntiCorruptionPolicies_List': 85.3587,
     '_3_4_2_AntiCompetitiveBehavior_List': 85.3587,
     '_3_4_3_BusinessEthicsTransparencyPayments_List': 85.3587,
     '_3_4_4_RegulatoryCapturePoliticalInfluence_List': 85.3587,
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
     'noWorkingCondition_List': 0,
     'nocustomerHealthSafety_List': 0,
     'provider': 'Chief Investment Officer',
     'relevancy10_List': 0.0,
     'relevancy11_List': 0.0,
     'relevancy12_List': 0.0,
     'relevancy13_List': 0.0,
     'relevancy14_List': 0.0,
     'relevancy15_List': 0.0,
     'relevancy16_List': 0.0,
     'relevancy17_List': 0.0,
     'relevancy18_List': 0.0,
     'relevancy19_List': 0.0,
     'relevancy1_List': 0.0,
     'relevancy20_List': 0.0,
     'relevancy21_List': 0.0,
     'relevancy22_List': 0.0,
     'relevancy23_List': 0.0,
     'relevancy24_List': 0.0,
     'relevancy25_List': 0.0,
     'relevancy26_List': 0.0,
     'relevancy27_List': 0.0,
     'relevancy28_List': 0.0,
     'relevancy29_List': 0.0,
     'relevancy2_List': 0.0,
     'relevancy30_List': 0.0,
     'relevancy31_List': 0.0,
     'relevancy32_List': 0.0,
     'relevancy33_List': 0.0,
     'relevancy34_List': 0.0,
     'relevancy35_List': 0.0,
     'relevancy36_List': 0.11,
     'relevancy37_List': 0.11,
     'relevancy38_List': 0.11,
     'relevancy39_List': 0.11,
     'relevancy3_List': 0.0,
     'relevancy40_List': 0.08,
     'relevancy41_List': 0.13,
     'relevancy42_List': 0.11,
     'relevancy43_List': 0.08,
     'relevancy44_List': 0.08,
     'relevancy45_List': 0.06,
     'relevancy46_List': 0.0,
     'relevancy47_List': 0.0,
     'relevancy48_List': 0.0,
     'relevancy49_List': 0.0,
     'relevancy4_List': 0.0,
     'relevancy50_List': 0.0,
     'relevancy5_List': 0.0,
     'relevancy6_List': 0.0,
     'relevancy7_List': 0.0,
     'relevancy8_List': 0.0,
     'relevancy9_List': 0.0,
     'relevancy_List': 60.0,
     'summary': 'Sustainable Water Fund Attracts $100 Million from Temasek, Microsoft ... \nand governance (ESG) standards will work together to develop a common \nframework ...',
     'timestamp': '2020-09-13 00:00:00',
     'title': 'Sustainable Water Fund Attracts $100 Million from Temasek ...',
     'topics': '41,36,37,38,39,40,42,43,44,45,46,47,48,49,50,7,',
     'url': 'https://www.ai-cio.com/news/sustainable-water-fund-attracts-100-million-temasek-microsoft/',
     'words': '549,350,257,283,226,,'
 }
]
```

This endpoint retrieves all news for a specified Company.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualNews3`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio
word | None | Yes | One of the Specific Words covered by Sensefolio
controv | None | Yes | One of the Specific Controversies covered by Sensefolio


<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## The list of **Sensefolio Categories** is the following:

'environment' <br> 
'social' <br> 
'governance'<br> 


## The list of **Sensefolio Topics** is the following:

**ENVIRONMENT TOPICS**<br>
'climate_change'<br> 
'sustainability'<br> 
'bio_div_water'<br>

**SOCIAL TOPICS**<br>
'health_safety'
'employee_standards' 
'community_responsibility'

**GOVERNANCE TOPICS**<br>
'leadership_mgmt'<br> 
'business_innov_perf'<br> 
'outside_activities'<br> 
'business_ethics'<br> 


## The list of **Sensefolio Controversies** is the following:

**Tax Fraud Controversies**<br>
'noTax' <br>

**Accounting Controversies**<br>
'noAccountingControv' <br>

**Insider Trading Controversies**<br>
'noInsiderTrading' <br>

**Child Labor Controversies**<br>
'noChildLabor' <br>

**Critical Countries Controversies**<br>
'criticalCountries' <br>

**Human Rights Controversies**<br>
'noHumanRights' <br>

**Environmental Controversies**<br>
'noEnvironmentControv' <br>

**Management Departures Controversies**<br>
'noMgmtDepartures' <br>

**Anti-Competition Controversies**<br>
'noAntiCompetition' <br>

**Business Ethics Controversies**<br>
'noBusinessEthics' <br>

**Intellectual Property Controversies**<br>
'noIPcontrov' <br>

**Management Compensation Controversies**<br>
'noMgmtCompensation' <br>

**Customer Health and Safety Controversies**<br>
'nocustomerHealthSafety' <br>

**Privacy Controversies**<br>
'noPrivacyControv' <br>

**Responsible Marketing Controversies**<br>
'noResponsibleMarketing' <br>

**Working Conditions Controversies**<br>
'noWorkingCondition'<br>




## Get All News for a Specific Company for a Specific Topic

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics_transparency"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualNews = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic="+str(topic)"+&
        criteria=&
        word=&
        controv="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)"+&
        end_date="+str(end_date)"+&
        category=&
        topic="+str(topic)"+&
        criteria=&
        word=&
        controv=",
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

This endpoint retrieves news for a specific company and for a specific Sensefolio topic.


### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualNews3`

### URL Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio
word | None | Yes | One of the Specific Words covered by Sensefolio
controv | None | Yes | One of the Specific Controversies covered by Sensefolio

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## The list of **Sensefolio Criteria** is the following:

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


# Tweets

## Get All Tweets for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualTweets = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualTweets?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic=&
        criteria=&
        word=&
        controv"
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualNews3?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)"+&
        end_date="+str(end_date)"+&
        category=&
        topic=&
        criteria=&
        word=&
        controv=",
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
     '_1_1_1_AirQuality_List': 90.0,
     '_1_1_2_ComplianceEnvironmentalRegulations_List': 90.0,
     '_1_1_3_EnergyMgmt_List': 90.0,
     '_1_1_4_FuelMgmt_List': 90.0,
     '_1_1_5_GHGemissions_List': 90.0,
     '_1_2_1_EnvironmentalImpactsAssetsOperations_List': 80.0,
     '_1_2_2_SupplierEnvironmentalAssessment_List': 80.0,
     '_1_2_3_EnvironBusinessDevelopment_List': 80.0,
     '_1_2_4_EvaluationEnvironKPI_List': 80.0,
     '_1_2_5_LifecycleImpactsProductsServices_List': 80.0,
     '_1_2_6_ProductPackaging_List': 80.0,
     '_1_2_7_ProductQualitySafety_List': 80.0,
     '_1_2_8_ResponsibleConsumptionProduction_List': 80.0,
     '_1_3_1_BiodiversityImpacts_List': 90.0,
     '_1_3_2_WaterWastewaterMgmt_List': 70.0,
     '_1_3_3_WasteHazardousMaterialsMgmt_List': 90.0,
     '_2_1_1_HealthSafety_List': None,
     '_2_2_1_FairLaborPractices_List': None,
     '_2_2_2_LaborMgmtRelations_List': None,
     '_2_2_3_TrainingEducation_List': None,
     '_2_2_4_DiversityEqualOpportunity_List': None,
     '_2_2_5_CompensationBenefits_List': None,
     '_2_2_6_RecruitmentDevelopmentRetention_List': None,
     '_2_3_1_AccessAffordability_List': None,
     '_2_3_2_CustomerHealthSafety_List': None,
     '_2_3_3_CustomerPrivacy_List': None,
     '_2_3_4_FairDisclosureLabeling_List': None,
     '_2_3_5_FairMarketingAdvertising_List': None,
     '_2_3_6_LocalCommunities_List': None,
     '_2_3_7_SocialImpactsAssetsOperations_List': None,
     '_2_4_1_ChildLabor_List': None,
     '_2_4_2_FreedomAssociationCollectiveBargaining_List': None,
     '_2_4_3_HumanRights_List': None,
     '_2_4_4_NonDiscrimination_List': None,
     '_2_4_5_RightsIndigenousPeoples_List': None,
     '_3_1_1_BoardLeadership_List': None,
     '_3_1_2_CeoExecutiveLeadership_List': None,
     '_3_1_3_ManagementLeadership_List': None,
     '_3_1_4_InternalControlRisks_List': None,
     '_3_2_1_EconomicPerformance_List': None,
     '_3_2_2_IndustryInnovationInfrastructure_List': None,
     '_3_2_3_MarketPresence_List': None,
     '_3_3_1_IndirectEconomicImpacts_List': 50.0,
     '_3_3_2_Partnerships_List': None,
     '_3_3_3_PeaceJusticeInstitutions_List': None,
     '_3_3_4_Transparency_List': None,
     '_3_4_1_AntiCorruptionPolicies_List': None,
     '_3_4_2_AntiCompetitiveBehavior_List': None,
     '_3_4_3_BusinessEthicsTransparencyPayments_List': None,
     '_3_4_4_RegulatoryCapturePoliticalInfluence_List': None,
     'company_idx': 1,
     'company_symbol': 'MSFT',
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
     'noWorkingCondition_List': 0,
     'nocustomerHealthSafety_List': 0,
     'relevancy_List': 85.0,
     'timestamp': '2020-09-29 20:06:19',
     'topics': '1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,43,',
     'tweet_content': 'Microsoft will replenish more water than it consumes by 2030 https://t.co/uNuHsFVxfd #sustainability',
     'tweet_link': None,
     'tweet_urlQuoted': None,
     'words': '226,282,433,,'
 }
]
```

This endpoint retrieves all tweets.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualTweets`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio
word | None | Yes | One of the Specific Words covered by Sensefolio
controv | None | Yes | One of the Specific Controversies covered by Sensefolio

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All Tweets for a Specific Company for a Specific Topic

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics_transparency"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualTweets = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualTweets?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic="+str(topic)+"&
        criteria=&
        word="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualTweets?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)"+&
        end_date="+str(end_date)"+&
        category=&
        topic="+str(topic)+"&
        criteria=&
        word=&
        controv=",
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
 '_1_1_1_AirQuality_List': 90.0,
 '_1_1_2_ComplianceEnvironmentalRegulations_List': 90.0,
 '_1_1_3_EnergyMgmt_List': 90.0,
 '_1_1_4_FuelMgmt_List': 90.0,
 '_1_1_5_GHGemissions_List': 90.0,
 '_1_2_1_EnvironmentalImpactsAssetsOperations_List': 70.0,
 '_1_2_2_SupplierEnvironmentalAssessment_List': 70.0,
 '_1_2_3_EnvironBusinessDevelopment_List': 70.0,
 '_1_2_4_EvaluationEnvironKPI_List': 70.0,
 '_1_2_5_LifecycleImpactsProductsServices_List': 70.0,
 '_1_2_6_ProductPackaging_List': 70.0,
 '_1_2_7_ProductQualitySafety_List': 70.0,
 '_1_2_8_ResponsibleConsumptionProduction_List': 70.0,
 '_1_3_1_BiodiversityImpacts_List': 90.0,
 '_1_3_2_WaterWastewaterMgmt_List': 90.0,
 '_1_3_3_WasteHazardousMaterialsMgmt_List': 90.0,
 '_2_1_1_HealthSafety_List': None,
 '_2_2_1_FairLaborPractices_List': None,
 '_2_2_2_LaborMgmtRelations_List': None,
 '_2_2_3_TrainingEducation_List': None,
 '_2_2_4_DiversityEqualOpportunity_List': None,
 '_2_2_5_CompensationBenefits_List': None,
 '_2_2_6_RecruitmentDevelopmentRetention_List': None,
 '_2_3_1_AccessAffordability_List': None,
 '_2_3_2_CustomerHealthSafety_List': None,
 '_2_3_3_CustomerPrivacy_List': None,
 '_2_3_4_FairDisclosureLabeling_List': None,
 '_2_3_5_FairMarketingAdvertising_List': None,
 '_2_3_6_LocalCommunities_List': None,
 '_2_3_7_SocialImpactsAssetsOperations_List': None,
 '_2_4_1_ChildLabor_List': None,
 '_2_4_2_FreedomAssociationCollectiveBargaining_List': None,
 '_2_4_3_HumanRights_List': None,
 '_2_4_4_NonDiscrimination_List': None,
 '_2_4_5_RightsIndigenousPeoples_List': None,
 '_3_1_1_BoardLeadership_List': None,
 '_3_1_2_CeoExecutiveLeadership_List': None,
 '_3_1_3_ManagementLeadership_List': None,
 '_3_1_4_InternalControlRisks_List': None,
 '_3_2_1_EconomicPerformance_List': None,
 '_3_2_2_IndustryInnovationInfrastructure_List': None,
 '_3_2_3_MarketPresence_List': None,
 '_3_3_1_IndirectEconomicImpacts_List': None,
 '_3_3_2_Partnerships_List': None,
 '_3_3_3_PeaceJusticeInstitutions_List': None,
 '_3_3_4_Transparency_List': None,
 '_3_4_1_AntiCorruptionPolicies_List': None,
 '_3_4_2_AntiCompetitiveBehavior_List': None,
 '_3_4_3_BusinessEthicsTransparencyPayments_List': None,
 '_3_4_4_RegulatoryCapturePoliticalInfluence_List': None,
 'company_idx': 1,
 'company_symbol': 'MSFT',
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
 'noWorkingCondition_List': 0,
 'nocustomerHealthSafety_List': 0,
 'relevancy_List': 60.0,
 'timestamp': '2020-09-29 14:00:35',
 'topics': '6,7,8,9,10,11,12,13,',
 'tweet_content': "Microsoft's Gretchen O'Hara, 17 Days of Sustainability https://t.co/GHGcEUHU5M",
 'tweet_link': None,
 'tweet_urlQuoted': None,
 'words': '433,,'
 },
 [...]
]
```

This endpoint retrieves tweets for a specific company and for a specific Sensefolio topic.


### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualTweets`

### URL Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio
word | None | Yes | One of the Specific Words covered by Sensefolio
controv | None | Yes | One of the Specific Controversies covered by Sensefolio






# G Company Reviews

## Get All G Company Reviews for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualGlassdoor = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualGlassdoor?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualGlassdoor?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic=&
        criteria=&
        word=",
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
    'CEO': 100.0,
     'Outlook': 100.0,
     'Recommends': 100.0,
     'advice': 'None',
     'careerOppStar': 25.0,
     'comBenefitsStar': 75.0,
     'company_idx': 1,
     'company_symbol': 'MSFT',
     'con': 'Many layers of management complexity, culture is skin deep and designed more for external perception than internal growth',
     'cultureStar': 25.0,
     'employee': 'Current Employee',
     'location': 'Seattle, WA',
     'overallStar': 50.0,
     'position': 'Director',
     'pro': 'Strong CEO, good vision, growth minded',
     'reviewNo': 'empReview_36328895',
     'srManagementStar': 50.0,
     'summary': 'Good but bureaucratic  company',
     'timestamp': '2020-09-24 00:00:00',
     'topics': '',
     'words': ',',
     'workLifeStar': 50.0
 },
 [...]
]
```

This endpoint retrieves all G Company Reviews.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualGlassdoor`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio
word | None | Yes | One of the Specific Words covered by Sensefolio

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All G Company Reviews for a Specific Company for a Specific Topic

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics_transparency"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualGlassdoor = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualGlassdoor?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic="+str(topic)+"&
        criteria=&
        word="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualGlassdoor?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic="+str(topic)+"&
        criteria=&
        word=",
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
    'CEO': 100.0,
     'Outlook': 100.0,
     'Recommends': 100.0,
     'advice': 'None',
     'careerOppStar': 25.0,
     'comBenefitsStar': 75.0,
     'company_idx': 1,
     'company_symbol': 'MSFT',
     'con': 'Many layers of management complexity, culture is skin deep and designed more for external perception than internal growth',
     'cultureStar': 25.0,
     'employee': 'Current Employee',
     'location': 'Seattle, WA',
     'overallStar': 50.0,
     'position': 'Director',
     'pro': 'Strong CEO, good vision, growth minded',
     'reviewNo': 'empReview_36328895',
     'srManagementStar': 50.0,
     'summary': 'Good but bureaucratic  company',
     'timestamp': '2020-09-24 00:00:00',
     'topics': '',
     'words': ',',
     'workLifeStar': 50.0
 },
 [...]
]
```

This endpoint retrieves all G Company Reviews for a specific company and for a specific Sensefolio topic.


### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualGlassdoor`

### URL Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio
word | None | Yes | One of the Specific Words covered by Sensefolio





# I Company Reviews

## Get All I Company Reviews for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 79
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualIndeed = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualIndeed?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic=&
        criteria=&
        word="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualIndeed?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic=&
        criteria=&
        word=",
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
     'category': 'Management',
     'company_idx': 79,
     'cons': 'Lack of diversity and advancement',
     'currentPast': '(Current Employee)',
     'dateDataGotRetrieved': '2020-10-24',
     'description': 'At gsk marietta, hourly employees are rarely promoted into management or salaried roles. If a promotion is achieved, it is usually in production for an off shift position. Consequently, there exist a culture of us versus them. No diversity in leadership roles in the production area.',
     'locations': 'Marietta, PA',
     'positions': 'Operator ',
     'pros': 'Great folks, benefits and pay',
     'ratings': 75.0,
     'reviewID': '1ek5abv2ss7ds800',
     'timestamp': '2020-10-08 00:00:00',
     'titles': 'Little chance for advancement'
 }
]
```

This endpoint retrieves all I Company Reviews.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualIndeed`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>

## Get All I Company Reviews for a Specific Company for a Specific Topic

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"
topic = "business_ethics_transparency"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualIndeed = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualIndeed?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic="+str(topic)+"&
        criteria=&
        word="
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualIndeed?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)+"&
        category=&
        topic="+str(topic)+"&
        criteria=&
        word=",
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
     'category': 'Culture',
     'company_idx': 1,
     'company_symbol': 'MSFT',
     'currentPast': '(Current Employee)',
     'dateDataGotRetrieved': '2020-09-26',
     'dateRaw': 'September 9, 2020',
     'description': 'Microsoft is no longer the Microsoft you thought it is. So much politics and management churn. No guidelines for layoffs but mangers constantly trying to kick people out.',
     'locations': 'Bellevue, WA',
     'positions': 'Software Development Engineer II',
     'reviewID': '1ehqbkj42rd6i800',
     'timestamp': '2020-09-09 00:00:00',
     'titles': 'Microsoft is resuming stack-ranking'
 }
]
```

This endpoint retrieves all I Company Reviews for a specific company and for a specific Sensefolio topic.


### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualIndeed`

### URL Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format
category | None | Yes | One of the Categories covered by Sensefolio
topic | None | Yes | One of the Topics covered by Sensefolio
criteria | None | Yes | One of the Criteria covered by Sensefolio







# Carbon Disclosure

## Get All Carbon Disclosure Information for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualCDP = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualCDP?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)
        , headers=headers).json()
```


```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualCDP?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date),
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
 {'company_idx': 1,
  'concreteScores': '90',
  'programs': 'Climate Change 2019',
  'scores': 'A',
  'status': 'Submitted',
  'timestamp': '2019-01-20 00:00:00',
  'years': '2019'},
  
 {'company_idx': 1,
  'concreteScores': None,
  'programs': 'Water Security 2019',
  'scores': 'Not applicable',
  'status': 'Submitted',
  'timestamp': '2019-02-03 00:00:00',
  'years': '2019'},
  
 {'company_idx': 1,
  'concreteScores': '90',
  'programs': 'Climate Change 2018',
  'scores': 'A',
  'status': 'Submitted',
  'timestamp': '2018-01-20 00:00:00',
  'years': '2018'},
  
 {'company_idx': 1,
  'concreteScores': '90',
  'programs': 'Water 2018',
  'scores': 'A',
  'status': 'Submitted',
  'timestamp': '2018-02-03 00:00:00',
  'years': '2018'}
]
```

This endpoint retrieves all Carbon Disclosure for a specific company and optionally in a certain timeframe.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualCDP`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>







# Violation Tracker

## Get All Violation Information for a Specific Company

```python
import requests

API_KEY = 'Your_API_Key'
company_idx = 1
start_date = "2015-01-01"
end_date = "2020-12-01"

headers = {
	   'x-api-key': API_KEY,
           'content-type': 'application/json'
	}

ActualViolationTracker = requests.get(
        "https://sensefolio-api.ue.r.appspot.com/ActualViolationTracker?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date)
        , headers=headers).json()
```

```javascript
var settings = {
  "url": "https://sensefolio-api.ue.r.appspot.com/ActualViolationTracker?
        company_idx="+str(company_idx)+"&
        start_date="+str(start_date)+"&
        end_date="+str(end_date),
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
 {'agency': 'Securities and Exchange Commission',
  'civil_or_criminal': 'civil',
  'company_idx': 1,
  'company_involved': 'Microsoft Corporation',
  'court': None,
  'dates': 'July 22, 2019',
  'info_source': 'https://www.sec.gov/litigation/admin/2019/34-86421.pdf',
  'offense_type': 'Foreign Corrupt Practices Act',
  'penalty_amount': '$16,565,150',
  'timestamp': '2019-07-22 00:00:00',
  'violation_description': 'If an online information source is not working, check the Violation Tracker Data Sources page for an updated link.'
  },
  
 {'agency': 'U.S. Attorney-Southern District of New York',
  'civil_or_criminal': 'criminal',
  'company_idx': 1,
  'company_involved': 'Microsoft Hungary',
  'court': None,
  'dates': 'July 22, 2019',
  'info_source': 'https://www.justice.gov/usao-sdny/pr/hungary-subsidiary-microsoft-corpor...',
  'offense_type': 'Foreign Corrupt Practices Act',
  'penalty_amount': '$8,751,795',
  'timestamp': '2019-07-22 00:00:00',
  'violation_description': "Microsoft Magyarorszag Szamitastechnikai Szolgaltato es Kereskedelmi Kft. (Microsoft Hungary), a wholly owned subsidiary of Microsoft Corporation, agreed to pay a criminal fine of more than $8.7 million to resolve an investigation into violations of the Foreign Corrupt Practices Act arising out of a bid rigging and bribery scheme in connection with the sale of Microsoft software licenses to Hungarian government agencies and the false recording of the corrupt payments as legitimate customer discounts on Microsoft Corporation's financial records."
  }
]
```

This endpoint retrieves all Violations for a specific company and optionally in a certain timeframe.

### HTTP Request

`GET https://sensefolio-api.ue.r.appspot.com/ActualViolationTracker`

### Query Parameters

Parameter | Default | Optional? | Description
--------- | ------- | ----------- | -----------
company_idx | None | No | The IDX assigned by Sensefolio for a company
start_date | None | Yes |Start Date using the "YYYY-MM-DD" format
end_date | None | Yes |End Date using the "YYYY-MM-DD" format

<aside class="success">
Remember — You can only access the Sensefolio API with your given API allowance.
</aside>





