# ClientEvents API

## ClientEvent

|Key|Value|
|---|---|
|id|ID|
|clientId|Client|
|eventId|Tracked event|
|properties|Additional properties for the data|
|created|Time for the tracking|

## List client event

List client events.

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/client_events|

### Parameters

|Key|Value|Default|
|---|---|---|
|clientId|Client ID||
|eventId|Tracked event||
|begin|Begin of time range||
|end|End of time range||
|exclusiveId|Exclusive ID for paging|(optional)|
|order|Sort order|ascending|
|limit|The max number of a page|100|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:ListClientEvent|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/client_events?clientId=Oy1FwLQJXXQWRrxo&eventId=Event:LBYtXQ26k6pHRZZB:Custom:Win&begin=2015-03-01T00%3A00%3A00%2B0000&end=2015-04-01T00%3A00%3A00%2B0000&exclusiveId=P6Ouhbk6kmLgJRVZ&order=ascending&limit=5&credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
[
	{"properties":{"opponent":"user_P6ODrb1HBZeIu0Oq"},"id":"P6OulcA0txE16of4","created":"2015-03-09T03:14:08+0000","clientId":"Oy1FwLQJXXQWRrxo","eventId":"Event:LBYtXQ26k6pHRZZB:Custom:Win"},
	{"properties":{"opponent":"CPU"},"id":"P6OuojrNioIwSRPu","created":"2015-03-09T03:14:20+0000","clientId":"Oy1FwLQJXXQWRrxo","eventId":"Event:LBYtXQ26k6pHRZZB:Custom:Win"},
	{"properties":{"opponent":"CPU"},"id":"P6Ouqa5odJ8phyOe","created":"2015-03-09T03:14:27+0000","clientId":"Oy1FwLQJXXQWRrxo","eventId":"Event:LBYtXQ26k6pHRZZB:Custom:Win"},
	{"properties":{"opponent":"user_P6ODl6a7EqFl4Xxm"},"id":"P6Ouszpyh4hD7wrp","created":"2015-03-09T03:14:36+0000","clientId":"Oy1FwLQJXXQWRrxo","eventId":"Event:LBYtXQ26k6pHRZZB:Custom:Win"},
	{"properties":{"opponent":"CPU"},"id":"P6OuueeeQ9QEgDrB","created":"2015-03-09T03:14:42+0000","clientId":"Oy1FwLQJXXQWRrxo","eventId":"Event:LBYtXQ26k6pHRZZB:Custom:Win"}
]
```

## Create client event

Create a new client event data point.

### Request

|Key|Value|
|---|---|
|Method|POST|
|URL|https://api.analytics.growthbeat.com/1/client_events|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

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
