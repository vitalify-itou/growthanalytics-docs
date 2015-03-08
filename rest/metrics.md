# Metrics API

## Metric

|Key|Value|
|---|---|
|id|Metric ID|
|name|Name for the metric|
|description|Description for the metric|
|query|query for the metric calculation|
|color|Color for the metric|
|created|Time the metric created|

## Get metric

Get metric of the metricId.

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/metrics/{metricId}|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:GetMetric|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/metrics/Metric:LBYtXQ26k6pHRZZB:Default:ActiveUser?credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"ActiveUser",
	"id":"Metric:LBYtXQ26k6pHRZZB:Default:ActiveUser",
	"query":{
		"type":"event",
		"direction":"up",
		"eventId":"Event:LBYtXQ26k6pHRZZB:Default:Open",
		"calculationQuery":{"type":"unique"},
		"filterQuery":{"type":"time","begin":{"type":"relative","origin":"begin","time":0},"end":{"type":"relative","origin":"end","time":0}}
	},
	"description":"The unique user",
	"created":"2015-01-22T05:27:27+0000",
	"color":null
}
```

## List metrics

List metrics

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/metrics|

### Parameters

|Key|Value|Default|
|---|---|---|
|parentMetricId|Metric ID of search root||
|order|Sort order|ascending|
|page|Page for the list|1|
|limit|Max count for a page|100|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:ListMetric|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/metrics?parentMetricId=Metric:LBYtXQ26k6pHRZZB&order=ascending&page=1&limit=5&credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
[
	{"name":"Custom","id":"Metric:LBYtXQ26k6pHRZZB:Custom","query":null,"created":"2015-01-22T05:27:27+0000","description":"Custom","color":null},
	{"name":"TutorialCompleted","id":"Metric:LBYtXQ26k6pHRZZB:Custom:TutorialCompleted","query":null,"created":"2015-02-11T07:54:36+0000","description":"Unique users who completed tutorial","color":null},
	{"name":"Default","id":"Metric:LBYtXQ26k6pHRZZB:Default","query":null,"created":"2015-01-22T05:27:27+0000","description":"Default","color":null},
	{"name":"ARPPU","id":"Metric:LBYtXQ26k6pHRZZB:Default:ARPPU","query":null,"created":"2015-01-22T05:27:37+0000","description":"Average revenue per pay user","color":null},
	{"name":"ARPU","id":"Metric:LBYtXQ26k6pHRZZB:Default:ARPU","query":null,"created":"2015-01-22T05:27:37+0000","description":"Average revenue per user","color":null}
]
```

## Update metric

Create a new metric or update the existing metric.

### Request

|Key|Value|
|---|---|
|Method|PUT|
|URL|https://api.analytics.growthbeat.com/1/metrics/{metricId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|name|Name for the metric|(Empty string)|
|description|Description for the metric|(Empty string)|
|query|query for the metric extraction||
|color|Color for the metric|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:UpdateMetric|

### Example

```
curl -X PUT -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/metrics/Metric:LBYtXQ26k6pHRZZB:Custom:Install' -d 'name=Install' -d 'description=Install users count' -d 'query={"type":"event","direction":"up","eventId":"Event:OvN0YPxSeadpLt6n:Default:Install","calculationQuery":{"type":"count"},"filterQuery":null}' -d 'color=0' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"Install",
	"id":"Metric:LBYtXQ26k6pHRZZB:Custom:Install",
	"query":{
		"type":"event",
		"direction":"up",
		"eventId":"Event:LBYtXQ26k6pHRZZB:Default:Install",
		"calculationQuery":{"type":"count"},
		"filterQuery":null
	},
	"description":"Install users count",
	"created":"2015-03-02T04:07:16+0000",
	"color":0
}
```

## Delete metric

Delete a metric.

### Request

|Key|Value|
|---|---|
|Method|DELETE|
|URL|https://api.analytics.growthbeat.com/1/metrics/{metricId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:DeleteMetric|

### Example

```
curl -X DELETE -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/metrics/Metric:LBYtXQ26k6pHRZZB:Custom:Install' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```
