# Tags API

## Tag

|Key|Value|
|---|---|
|id|Tag ID|
|name|Name for the tag|
|description|Description for the tag|
|created|Time the tag created|

## Get tag

Get tag of the tagId.

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/tags/{tagId}|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:GetTag|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/tags/Tag:LBYtXQ26k6pHRZZB:Default:Level?credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"Level",
	"id":"Tag:LBYtXQ26k6pHRZZB:Default:Level",
	"created":"2015-01-22T05:27:27+0000",
	"description":"Level of the user"
}
```

## List tags

List tags

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/tags|

### Parameters

|Key|Value|Default|
|---|---|---|
|parentTagId|Tag ID of search root||
|order|Sort order|ascending|
|page|Page for the list|1|
|limit|Max count for a page|100|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:ListTag|

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/tags?parentTagId=Tag:LBYtXQ26k6pHRZZB&order=ascending&page=1&limit=5&credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
[
	{"name":"Custom","id":"Tag:LBYtXQ26k6pHRZZB:Custom","created":"2015-01-22T05:27:27+0000","description":"Custom"},
	{"name":"Gender","id":"Tag:LBYtXQ26k6pHRZZB:Custom:Gender","created":"2015-02-11T08:07:01+0000","description":"Gender"},
	{"name":"Default","id":"Tag:LBYtXQ26k6pHRZZB:Default","created":"2015-01-22T05:27:27+0000","description":"Default"},
	{"name":"FrindCount","id":"Tag:LBYtXQ26k6pHRZZB:Default:FriendCount","created":"2015-01-22T05:27:27+0000","description":"The number of friends"},
	{"name":"Level","id":"Tag:LBYtXQ26k6pHRZZB:Default:Level","created":"2015-01-22T05:27:27+0000","description":"Level"}
]
```

## Update tag

Create a new tag or update the existing tag.

### Request

|Key|Value|
|---|---|
|Method|PUT|
|URL|https://api.analytics.growthbeat.com/1/tags/{tagId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|name|Name for the tag|(Empty string)|
|description|Description for the tag|(Empty string)|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:UpdateTag|

### Example

```
curl -X PUT -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/tags/Tag:LBYtXQ26k6pHRZZB:Custom:CurrentStage' -d 'name=Crrent stage' -d 'description=The stage user is currently playing' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"name":"Crrent stage",
	"id":"Tag:LBYtXQ26k6pHRZZB:Custom:CurrentStage",
	"created":"2015-03-02T00:45:48+0000",
	"description":"The stage user is currently playing"
}
```

## Delete tag

Delete a tag.

### Request

|Key|Value|
|---|---|
|Method|DELETE|
|URL|https://api.analytics.growthbeat.com/1/tags/{tagId}|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:DeleteTag|

### Example

```
curl -X DELETE -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/tags/Tag:LBYtXQ26k6pHRZZB:Custom:CurrentStage' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```
