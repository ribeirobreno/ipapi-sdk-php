# ip-api.com PHP SDK

A simple API for ip-api.com using PHP

## Installation

Just require the package using composer.

```sh
composer require naylonkessler/ipapi-sdk-php
```

## Using the package

Just import, instantiate and call:

```php
<?php

use IpApi\IpApi;

$api = new IpApi();
$response = $api->locate('ip or address');
```

### The \IpApi\Response object

The response object has an schema returned composed by the following fields by default:

- status: Status of operation;
- country: Country of address;
- countryCode: Country code of address;
- region: Region abbr (state) of address;
- regionName": Region name (state) of address;
- city: City of address;
- zip: Zipcode of address;
- lat: Latitude of address;
- lon: Longitude of address;
- timezone: Timezone related to address;
- isp: The ISP organization;
- org: The organization name related to address;
- as: The AS number and name;
- query: The address or IP used on query.

The response object has some others methods and features:

```php
// Convert the object to an array
$data = $response->toArray();

// Fill the object with received array data
$response->fill([
    'propertyOne' => 'Value one',
    'propertyTwo' => 'Value two',
]);

// JSON encode
$json = json_encode($response);
```
