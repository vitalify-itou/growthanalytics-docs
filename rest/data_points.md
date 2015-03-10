# Data Points API

## Data Point

|Key|Value|
|---|---|
|category|Category for the value|
|value|Value of this data point|

## List data points

List data points

### Request

|Key|Value|
|---|---|
|Method|GET|
|URL|https://api.analytics.growthbeat.com/1/data_points|

### Parameters

|Key|Value|Default|
|---|---|---|
|dataPointQuery|Query to fetch data points||
|credentialId|Credential ID for authentication||

### Required permission

|Resource|Action|
|---|---|
|||

### Example

```
curl -X GET -H 'Accept: application/json' 'https://api.analytics.growthbeat.com/1/data_points?dataPointQuery=%7B%22type%22%3A%22metric%22%2C%22begin%22%3A%7B%22type%22%3A%22absolute%22%2C%22time%22%3A%222015-01-01T00%3A00%3A00%2B0000%22%7D%2C%22end%22%3A%7B%22type%22%3A%22absolute%22%2C%22time%22%3A%222015-01-10T00%3A00%3A00%2B0000%22%7D%2C%22period%22%3A86400000%2C%22metricQuery%22%3A%7B%22type%22%3A%22metric%22%2C%22direction%22%3A%22up%22%2C%22metricId%22%3A%22Metric%3ALBYtXQ26k6pHRZZB%3ADefault%3AActiveUser%22%7D%7D&credentialId=nMdZa0PfT1rmxHEh4MTnpfG6ncxtiTgY'
```

```
[
	{"value":421.0,"category":"2015-01-01T09:00:00+0000"},
	{"value":420.0,"category":"2015-01-02T09:00:00+0000"},
	{"value":399.0,"category":"2015-01-03T09:00:00+0000"},
	{"value":408.0,"category":"2015-01-04T09:00:00+0000"},
	{"value":418.0,"category":"2015-01-05T09:00:00+0000"},
	{"value":424.0,"category":"2015-01-06T09:00:00+0000"},
	{"value":416.0,"category":"2015-01-07T09:00:00+0000"},
	{"value":398.0,"category":"2015-01-08T09:00:00+0000"},
	{"value":393.0,"category":"2015-01-09T09:00:00+0000"}
]
```

