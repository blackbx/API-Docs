---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the BlackBX API! You can use our API to access BlackBX API endpoints, which can get various pieces of information.

At the moment, we only offer support for Shell!

# Authentication With BlackBX

> To authorize, use this code:rwar

```Shell
With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: /oauth"
```

```shell
curl "http://blackbx.io/api/oauth/token"
  -H "Authorization: apiKey"
```

> Make sure to replace `meowmeowmeow` with your API key.

The BlackBX API uses API keys to allow access to the API. You can register a new BlackBX API key at our [developer portal](http://example.com/oauth/token).

BlackBX expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: apiKey`


This endpoint authorizes you with our service.

<aside class="notice">
You must replace <code>apiKey</code> with your personal API key.
</aside>

# Customer

<aside class="notice">
  This object requires admin access
</aside>

## Create Customer

### HTTP Request

`POST http://example.com/members/`

### Query Parameters

Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
Email     |    No    | string   | Email associated with Customer
First     |    No    | string   | First Name associated with Customer
Last      |    No    | string   | Last Name associated with Customer
Company   |    No    | string   | Company associated with Customer
role      |    No    | bool     | Role

## Get Customer
### HTTP Request

`GET http://example.com/members/<user_id>`

### Query Parameters

Parameter |  Description
--------- |  -----------
user_id | The user id of the customer.

## Update Customer

### HTTP Request

`PUT http://example.com/members/<user_id>`

### Query Parameters

Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
user_id   |    Yes   | string   | The user id of the customer to be updated.
Email     |    No    | string   | Email associated with Customer
First     |    No    | string   | First Name associated with Customer
Last      |    No    | string   | Last Name associated with Customer
Company   |    No    | string   | Company associated with Customer
role      |    No    | bool     | Role

# Locations

In BlackBX, we assign device locations serial numbers where we can get all information relating to this location using the serial number.

## Retreive Specific Location

```shell
curl "http://example.com/locations/71B1066C148A"
  -H "Authorization: apiKey"
```

> The above command returns JSON structured like this:

### HTTP Request

`GET http://example.com/locations/<serial_number>`

### Query Parameters

Parameter |  Description
--------- |  -----------
serial_number | The serial number that represents the location.

## Update a Location

```shell
curl "http://example.com/locations/2"
  -H "Authorization: apiKey"
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

This endpoint updates a specific kitten.

### HTTP Request

`PUT http://example.com/locations/<serial_number>`

### URL Parameters

Parameter | Description
--------- | -----------
serial_number | The ID of the location to update

## Delete a Location

```shell
curl "http://example.com/locations/2"
  -H "Authorization: apiKey"
```

> The above command returns JSON structured like this:



This endpoint updates a specific kitten.

### HTTP Request

`DELETE http://example.com/locations/<serial_number>`

### URL Parameters

Parameter | Description
--------- | -----------
serial_number | The ID of the location to delete

# Stripe 
<aside class="notice">
  This object requires admin access
</aside>

This section is for accessing our Stripe integration, where we have a CRUD for Customers, Charges &amp; Cards

## Authorizing with Stripe
### HTTP Request 

'GET http://example.com/stripe/authorize'

### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
uid       |    Yes   | string   | The user id of the customer to connected to Stripe.

## Customers

### Create New Customer

### HTTP Request

'POST http://example.com/stripe/customer'

### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
id        |    Yes   | int      | The user id of the customer to be connected to Stripe.
serial    |    Yes   | string   | The location where Customer is signing up

### Update Customer in Stripe

### HTTP Request

'PUT http://example.com/stripe/customer'

## Cards

### Create New Card

### HTTP Request

'POST http://example.com/stripe/card'

### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
customerId|    Yes   | string   | The Stripe Customer ID of user.
card      |    Yes   | object   | Contains Name, Card Number, CVC &amp; Expiration Date

### Get Cards

### HTTP Request

'GET http://example.com/stripe/card/{customerId}'
### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
customerId|   Yes    | string   | The Stripe Customer ID of user

### Delete Card

### HTTP Request
'DELETE http://example.com/stripe/card/{cardId}/{customerId}'

### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
cardId    |   Yes    | string   | The ID of the card to delete
customerId|   Yes    | string   | The Stripe Customer ID of user

## Charges

### Create New Charge

### HTTP Request

### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
user_id   |    Yes   | string   | The user id of the customer to be updated.
Email     |    No    | string   | Email associated with Customer
First     |    No    | string   | First Name associated with Customer
Last      |    No    | string   | Last Name associated with Customer
Company   |    No    | string   | Company associated with Customer
role      |    No    | bool     | Role

### Update Existing Charge

### HTTP Request

'PUT http://example.com/stripe/charge/{chargeId}/{customerId}'

### URL Parameters
Parameter | Required | Type     | Description
--------- | -------- | ----     | -----------
user_id   |    Yes   | string   | The user id of the customer to be updated.
Email     |    No    | string   | Email associated with Customer
First     |    No    | string   | First Name associated with Customer
Last      |    No    | string   | Last Name associated with Customer
Company   |    No    | string   | Company associated with Customer
role      |    No    | bool     | Role



