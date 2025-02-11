---
title: Spincast API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php
  - javascript

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:

[//]: # (  - errors)

search: true

code_clipboard: true

meta:
  - name: Documentation for the Spincast API
    content: Documentation for the Spincast API
---

# Introduction

Welcome to the Spincast API documentation.

We have language bindings in Shell, PHP, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> Authorization header example:

```shell
curl "api_endpoint_here" \
  --header "Authorization: Bearer qwertyuiopasdfghjkl"
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Authorization", "Bearer qwertyuiopasdfghjkl");
```

```php
curl_setopt_array($curl, array(
  CURLOPT_URL => 'api_endpoint_here',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Authorization: Bearer qwertyuiopasdfghjkl',
  ),
));
```

> Make sure to replace `qwertyuiopasdfghjkl` with your API key.

Spincast uses API keys to allow access to the API. An API key can be obtained by [registering](https://www.spincast.io/register) for an account and creating a key.

Spincast expects the API key to be included in all API requests to the server in an `Authorization` header as a Bearer token:

`Authorization: Bearer qwertyuiopasdfghjkl`

<aside class="notice">
You must replace <code>qwertyuiopasdfghjkl</code> with your personal API key.
</aside>

# User

## Get Current User

```shell
curl --location --request GET 'https://api.spincast.io/api/v1/users' \
--header 'Authorization: Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy'
```
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.spincast.io/api/v1/users',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/vnd.api+json',
    'Authorization: Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Accept", "application/vnd.api+json");
myHeaders.append("Authorization", "Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.spincast.io/api/v1/users", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "type": "users",
      "id": "1",
      "attributes": {
        "name": "John Doe",
        "email": "johnDown@sometld.com",
        "created_at": "2021-12-30 22:30:40",
        "updated_at": "2021-12-30 22:50:36"
      },
      "links": {
        "self": "https://api.spincast.io/api/v1/users/1"
      }
    }
  ]
}
```

Retrieve the current user (identified by API Key).

### HTTP Request

`GET https://api.spincast.io/api/v1/users`

# Workout

## Get Workouts

```shell
curl --location --request GET 'https://api.spincast.io/api/v1/workouts' \
--header 'Accept: application/vnd.api+json' \
--header 'Content-Type: application/vnd.api+json' \
--header 'Authorization: Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Accept", "application/vnd.api+json");
myHeaders.append("Content-Type", "application/vnd.api+json");
myHeaders.append("Authorization", "Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy");

var raw = "";

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.spincast.io/api/v1/workouts", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.spincast.io/api/v1/workouts',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/vnd.api+json',
    'Content-Type: application/vnd.api+json',
    'Authorization: Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "type": "workouts",
      "id": "181",
      "attributes": {
        "createdAt": "2021-12-17T05:40:41.000000Z",
        "updatedAt": "2021-12-17T05:40:41.000000Z",
        "pelotonId": "e43bfda89ab541ae97821f295a8b1903"
      },
      "links": {
        "self": "https://api.spincast.io/api/v1/workouts/181"
      }
    },
    {
      "type": "workouts",
      "id": "182",
      "attributes": {
        "createdAt": "2021-12-17T05:40:41.000000Z",
        "updatedAt": "2021-12-17T05:40:41.000000Z",
        "pelotonId": "5c01724c4cca4bbf90bc2e0815360855"
      },
      "links": {
        "self": "https://api.spincast.io/api/v1/workouts/182"
      }
    }
  ]
}
```

Retrieve all the workouts for the current user (identified by API Key).

### HTTP Request

`GET http://api.spincast.io/api/v1/workouts`

## Queue Workout

```shell
curl --location --request POST 'https://api.spincast.io/queue/181' \
--header 'Accept: application/vnd.api+json' \
--header 'Content-Type: application/vnd.api+json' \
--header 'Authorization: Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Accept", "application/vnd.api+json");
myHeaders.append("Content-Type", "application/vnd.api+json");
myHeaders.append("Authorization", "Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy");

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.spincast.io/queue/181", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.spincast.io/queue/181',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/vnd.api+json',
    'Content-Type: application/vnd.api+json',
    'Authorization: Bearer 36|Krc1ED0YfBamYWmyH2aoueoxdCNzjVc4IEgfaiOy',
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

> The above command returns JSON structured like this:

```json

```

Requeue a `workout` to be sent to Zapier.

Parameter | Required | Description
--------- |----------| -----------
id | true     | `workout` identifier

### HTTP Request

`POST https://api.spincast.io/queue/{workout.id}`
