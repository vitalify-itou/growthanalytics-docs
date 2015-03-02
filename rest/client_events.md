# ClientEvents API

## ClientEvent

|Key|Value|
|---|---|
|id|ID|
|clientId|Client|
|eventId|Tracked event|
|properties|Additional properties for the data|
|created|Time for the tracking|

## Create client event

Create a new client event data point.

### Request

|Key|Value|
|---|---|
|Method|POST|
|URL|https://api.analytics.growthbeat.com/1/client_events|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

The name is used to display on dashboard.

|Key|Value|Default|
|---|---|---|
|clientId|Client ID||
|eventId|Tracked event||
|properties[key]|property for the key|(optional)|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:CreateClientEvent|

### Example

```
curl -X POST -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/client_events' -d 'clientId=Oy1FwLQJXXQWRrxo' -d 'eventId=Event:LBYtXQ26k6pHRZZB:Custom:Win' -d 'properties[opponent]=CPU' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"properties":{
		"opponent":"CPU"
	},
	"id":"P5iQN7NLW8iY7W5t",
	"created":"2015-03-02T00:56:14+0000",
	"eventId":"Event:LBYtXQ26k6pHRZZB:Custom:Win",
	"clientId":"Oy1FwLQJXXQWRrxo"
}
```
