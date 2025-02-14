# openapi-client
Financial Modeling Prep API

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >= 3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import openapi_client
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import openapi_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import openapi_client
from pprint import pprint
from openapi_client.api import company_valuation_api
from openapi_client.model.company_profile import CompanyProfile
from openapi_client.model.company_quote import CompanyQuote
# Defining the host is optional and defaults to https://financialmodelingprep.com/api/v3
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "https://financialmodelingprep.com/api/v3"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: api_key
configuration.api_key['api_key'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['api_key'] = 'Bearer'


# Enter a context with an instance of the API client
with openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = company_valuation_api.CompanyValuationApi(api_client)
    symbol = "symbol_example" # str | Name of ticker

    try:
        # Get the Company profile
        api_response = api_instance.profile(symbol)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CompanyValuationApi->profile: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://financialmodelingprep.com/api/v3*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CompanyValuationApi* | [**profile**](docs/CompanyValuationApi.md#profile) | **GET** /profile/{symbol} | Get the Company profile
*CompanyValuationApi* | [**quote**](docs/CompanyValuationApi.md#quote) | **GET** /quote/{symbol} | Get the Company Quote
*HistoryApi* | [**daily_prices**](docs/HistoryApi.md#daily_prices) | **GET** /historical-price-full/{symbol} | Get Ticker price
*HistoryApi* | [**intra_day_prices**](docs/HistoryApi.md#intra_day_prices) | **GET** /historical-chart/{resolution}/{symbol} | Get Ticker price
*ListApi* | [**list_symbols**](docs/ListApi.md#list_symbols) | **GET** /{type}/list | Get list of symbols


## Documentation For Models

 - [CompanyProfile](docs/CompanyProfile.md)
 - [CompanyQuote](docs/CompanyQuote.md)
 - [EndOfDayPrice](docs/EndOfDayPrice.md)
 - [EndOfDayPriceHistory](docs/EndOfDayPriceHistory.md)
 - [OHVCVPrice](docs/OHVCVPrice.md)
 - [OHVCVPrices](docs/OHVCVPrices.md)
 - [Symbol](docs/Symbol.md)


## Documentation For Authorization


## api_key

- **Type**: API key
- **API key parameter name**: apikey
- **Location**: URL query string


## Author

sam@sddproductions.com


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in openapi_client.apis and openapi_client.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from openapi_client.api.default_api import DefaultApi`
- `from openapi_client.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import openapi_client
from openapi_client.apis import *
from openapi_client.models import *
```

