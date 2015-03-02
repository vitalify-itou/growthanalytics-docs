# ClientTags API

## ClientTag

|Key|Value|
|---|---|
|clientId|Client|
|tagId|Tag ID|
|value|Value of the tag|
|created|Time for the tracking|

## Create client tag

Update the value of the tag.

### Request

|Key|Value|
|---|---|
|Method|POST|
|URL|https://api.analytics.growthbeat.com/1/client_tags|
|Content-Type|application/x-www-form-urlencoded|

### Parameters

|Key|Value|Default|
|---|---|---|
|clientId|Client ID||
|tagId|Tag ID||
|value|Value of the tag||
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|Resource:Growthbeat:Application:{applicationId}|Action:GrowthAnalytics:CreateClientTag|

### Example

```
curl -X POST -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' 'https://api.analytics.growthbeat.com/1/client_tags' -d 'clientId=Oy1FwLQJXXQWRrxo' -d 'tagId=Tag:LBYtXQ26k6pHRZZB:Default:Level' -d 'value=15' -d 'credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
{
	"value":"15",
	"updated":"2015-03-02T03:44:18+0000",
	"tagId":"Tag:LBYtXQ26k6pHRZZB:Default:Level",
	"clientId":"Oy1FwLQJXXQWRrxo"
}
```
