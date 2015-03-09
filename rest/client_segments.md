# ClientSegments API

## ClientSegment

|Key|Value|
|---|---|
|clientId|Client ID|
|segmentId|Segment ID|

## Get client segment

Get client segments.

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/client_segments|

### Parameters

|Key|Value|Default|
|---|---|---|
|clientId|Client ID||
|segmentId|SegmentId||
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|||

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/client_segments?clientId=Oy1FwLQJXXQWRrxo&segmentId=Segment:LBYtXQ26k6pHRZZB:Default:All&credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"clientId":"Oy1FwLQJXXQWRrxo",
	"segmentId":"Segment:LBYtXQ26k6pHRZZB:Default:All"
}
```
