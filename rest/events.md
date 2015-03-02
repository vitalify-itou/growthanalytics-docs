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

## Update event

Create a new event or update the existing event.

### Request

|Key|Value|
|---|---|
|Method|PUT|
|URL|https://api.analytics.growthbeat.com/1/events/{eventId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

The name is used to display on dashboard.

|Key|Value|Default|
|---|---|---|
|name|Name for the event|(Empty string)|
|description|Description for the event|(Empty string)|
|credentialId|Credential ID for authentication||

### Required permission

The eventId of resource is for the event of credential.

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:UpdateEvent|

### Example

```
curl -X PUT -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/events/Event:LBYtXQ26k6pHRZZB:Custom:Win' -d 'name=Win' -d 'description=Win the battle' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"Win",
	"id":"Event:LBYtXQ26k6pHRZZB:Custom:Win",
	"created":"2015-03-02T00:35:16+0000",
	"description":"Win the battle"
}
```

## Delete event

Delete a event.

### Request

|Key|Value|
|---|---|
|Method|DELETE|
|URL|https://api.analytics.growthbeat.com/1/events/{eventId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

The eventId of resource is for the event of credential.

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:DeleteEvent|

### Example

```
curl -X DELETE -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/events/Event:LBYtXQ26k6pHRZZB:Custom:Win' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```
