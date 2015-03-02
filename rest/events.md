# Events API

## Event

|Key|Value|
|---|---|
|id|Event ID|
|name|Name for the event|
|description|Description for the event|
|created|Time the event created|

## Get event

Get event of the eventId.

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/events/{eventId}|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:GetEvent|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/events/Event:LBYtXQ26k6pHRZZB:Default:Open?credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"Open",
	"id":"Event:LBYtXQ26k6pHRZZB:Default:Open",
	"created":"2015-01-22T05:27:27+0000",
	"description":"Open the app"
}
```
