---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Some Text about the purpose of Athena


# Encompass

All endpoints in this section handle calls to the Encompass API

## Issue Token

```shell
curl "http://example.com/api/encompass/token/issue
  -H "username: sampleuser"
  -H "password: 1Password""
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "access_token": "6v8wKWREGjeECskvcibQtdiO7tWn",
 		"token_type": "Bearer"
  }
```

 Used by the client application to obtain an access token. (Taken from Encompass API Documentation)


### HTTP Request

`GET http://example.com/api/encompass/token/issue`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
username | null | Username used to login to Encompass
password | null | Password used to login to Encompass

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Revoke Token

```shell
curl "http://example.com/api/encompass/token/revoke
  -H "token:6v8wKWREGjeECskvcibQtdiO7tWn "
"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

 Used by the application to revoke an access token and invalidate the associated session. (Taken from Encompass API Documentation)

### HTTP Request

`GET http://example.com/api/encompass/token/revoke`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
token | null | Encompass Token that will be revoked



## Token Introspection

```shell
curl "http://example.com/api/encompass/token/introspection
  -H "token:6v8wKWREGjeECskvcibQtdiO7tWn "
"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

Used by the client application to validate an access token and retrieve the associated metadata. (Taken from Encompass API Documentation)

### HTTP Request

`GET http://example.com/api/encompass/token/introspection`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
token | null | Encompass Token that will be introspected




## Get Loan
```shell
curl "http://example.com/api/encompass/loan
  -H "token:6v8wKWREGjeECskvcibQtdiO7tWn "
  -H "loanID:123456 "
"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

Used to query Encompass database for specified fields 

### HTTP Request

`GET http://example.com/api/encompass/loan`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
token | null | Encompass Token that will be introspected
loanGUID | null | Encompass Loan ID
desiredFields | null | TODO:  This should be a list of the fields we want from the particular loan



## Reporting Pipeline
```shell
curl "http://example.com/api/encompass/pipeline/reporting

  -H "token:6v8wKWREGjeECskvcibQtdiO7tWn "
  -H "filterType:Funded "
"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

Used to query Encompass database for all loans that are in the state specified but the "filterType" header parameter.  


### HTTP Request

`GET http://example.com/api/encompass/pipeline/reporting`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
token | null | Encompass Token that will be introspected
filterType | null | Current status of loans requesting.  (Funded, Locked, Pre Approval, etc)


## Mobile Pipeline
```shell
curl "http://example.com/api/encompass/pipeline/mobile

  -H "token:6v8wKWREGjeECskvcibQtdiO7tWn "
  -H "userID: test@vdmc.net "
  -H "userType: Realtor "
  -H "deviceID: gr32425grw-465hdb23-345234gv-74bsdadczyu6 "
"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

Used to query Encompass database for loans that have the userType set to the user ID.  For example if the userType is Realtor and the userID is test@vdmc.net, this end point will query all loans to see where the Realtor Email address is equal to test@vdmc.net.

### HTTP Request

`GET http://example.com/api/encompass/pipeline/mobile`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
token | null | Encompass Token that will be introspected
userID | null | Email of address of user whose pipeline being requested
userType | null | Type of user whose pipeline being requested (Borrower, Realtor, LO)
deviceID | null | Device ID of mobile device that is accessing the endpoint (Required for push notifications)

#Communication
##Send Push Notification
```shell
curl "http://example.com/api/communication/sendNotification

  -H "message:Test Message "
  -H "deviceID: gr32425grw-465hdb23-345234gv-74bsdadczyu6"

"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

Used to send Notification to specified DeviceIDs

### HTTP Request

`GET http://example.com/api/communication/sendNotification`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
message|''| Message to be sent to devices
deviceID | null | Device ID of mobile device that is accessing the endpoint (Required for push notifications)

##Send SMS
```shell
curl "http://example.com/api/communication/sendSMS

  -H "message:Test Message "
  -H "phoneNumber:+15555555555"

"
```

```javascript
//TBD
```

> The above command returns JSON structured like this:

```json
  {
 	  "TBD": null 
  }
```

Used to send SMS messages to specified phone number

### HTTP Request

`GET http://example.com/api/communication/sendSMS`

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
message|''| Message to be sent to devices
phoneNumber | null | Phone Number of device to receive SMS message

#Top Of Mind

#Floify
These are viewable by us as developer, but we will need to have our own API definition that will be sure to keep Floifys API safe.
##Get Floify Flows
   [https://developer.floify.com/v1.0/reference#flows] (https://developer.floify.com/v1.0/reference#flows)
##Get Loan Metadata
 [https://developer.floify.com/v1.0/reference#loan-metadata] (https://developer.floify.com/v1.0/reference#loan-metadata)
## Start Loan
 [https://developer.floify.com/v1.0/reference#start] (https://developer.floify.com/v1.0/reference#start)
## Download Floify Document
 [https://developer.floify.com/v1.0/reference#download] (https://developer.floify.com/v1.0/reference#download)
## Upload One Off Floify Document
 [https://developer.floify.com/v1.0/reference#upload-onoff] (https://developer.floify.com/v1.0/reference#upload-onoff)
## Upload Expected Floify Document
 [https://developer.floify.com/v1.0/reference#upload] (https://developer.floify.com/v1.0/reference#upload)

#Utilities

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
