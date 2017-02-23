# Analytics

The `Analytics` class from the `mapbox.services.analytics` module provides
access to the Mapbox Analytics API. You can also import it directly from the
`mapbox` module.

```python
>>> from mapbox import Analytics

```


See https://www.mapbox.com/api-documentation/#analytics for general documentation of the API.

Your Mapbox access token should be set in your environment; see the [access
tokens](access_tokens.md) documentation for more information.

## Analytics methods

The methods of `Analytics` class that provide access to the Analytics API return an instance of 
[`requests.Response`](http://docs.python-requests.org/en/latest/api/#requests.Response). `Analytics` response also include the `json()` method which returns Python data parsed from API.

## Usage

The Mapbox Analytics API is used to get API usage for services by resource. It returns counts per day for given resource and period.

```python
>>> analytics = Analytics()

```

The input to `analytics` method are resource_type, username, id, period, access_token.

```python
>>> resource_type = 'accounts'
>>> username = 'sanjayb'
>>> id = ''
>>> period = ('2016-03-22T00:00:00.000Z', '2016-03-24T00:00:00.000Z')
>>> access_token = 'abc'

```

``` python
>>> response = analytics.analytics(resource_type, username, id, period, access_token)
>>> response.status_code
401

```