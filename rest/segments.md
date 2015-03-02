# Segments API

## Segment

|Key|Value|
|---|---|
|id|Segment ID|
|name|Name for the segment|
|description|Description for the segment|
|query|query for the segment extraction|
|created|Time the segment created|

## Get segment

Get segment of the segmentId.

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/segments/{segmentId}|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:GetSegment|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/segments/Segment:LBYtXQ26k6pHRZZB:Default:All?credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"All",
	"id":"Segment:LBYtXQ26k6pHRZZB:Default:All",
	"query":{
		"type":"application",
		"note":null,
		"applicationId":"LBYtXQ26k6pHRZZB"
	},
	"created":"2015-01-22T05:28:31+0000",
	"description":"All users"
}
```

## Update segment

Create a new segment or update the existing segment.

### Request

|Key|Value|
|---|---|
|Method|PUT|
|URL|https://api.analytics.growthbeat.com/1/segments/{segmentId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

The name is used to display on dashboard.

|Key|Value|Default|
|---|---|---|
|name|Name for the segment|(Empty string)|
|description|Description for the segment|(Empty string)|
|query|query for the segment extraction||
|credentialId|Credential ID for authentication||

### Required permission

The segmentId of resource is for the segment of credential.

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:UpdateSegment|

### Example

```
curl -X PUT -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/segments/Segment:LBYtXQ26k6pHRZZB:Custom:Level5OrMore' -d 'name=Level 5 or more' -d 'description=The users whose level is more than 5' -d 'query={"type":"tag","tagId":"Tag:OvN0YPxSeadpLt6n:Default:Level","operator":"greater_equal","value":"5"}' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"Level 5 or more",
	"id":"Segment:LBYtXQ26k6pHRZZB:Custom:Level5OrMore",
	"query":{
		"type":"tag",
		"note":null,
		"tagId":"Tag:LBYtXQ26k6pHRZZB:Default:Level",
		"operator":"greater_equal",
		"value":"5"
	},
	"description":"The users whose level is more than 5",
	"created":"2015-03-02T03:58:40+0000"
}
```

## Delete segment

Delete a segment.

### Request

|Key|Value|
|---|---|
|Method|DELETE|
|URL|https://api.analytics.growthbeat.com/1/segments/{segmentId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

The segmentId of resource is for the segment of credential.

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:DeleteSegment|

### Example

```
curl -X DELETE -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/segments/Segment:LBYtXQ26k6pHRZZB:Custom:Level5OrMore' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```
