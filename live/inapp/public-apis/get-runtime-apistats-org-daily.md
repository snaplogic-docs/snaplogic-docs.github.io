# GET /runtime/api-stats/\{org\}/daily {#get-runtime-apistats-org-daily .concept}

retrieves the daily metrics of Tasks running on the specified date.

## Overview { .section}

This API retrieves the daily metrics of Tasks running on the specified date.

## Prerequisites { .section}

-   Read access to the assets requested

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/runtime/api-stats/\{org\}/daily?{query_parameters}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`org`|**Required.** The name of the SnapLogic Org.|

Query Parameters

|Key|Type|Description|
|---|----|-----------|
|`date_time`|string|The date in UTC format. Default: The current date.

 Example: `date_time=2021-12-31T01:01:01`

|

Request Header

Specify Basic Auth for authorization.

``` {#d73e705 .normalize-space}
   Authorization: Basic {your_encoded_security_credentials}

```

Request Body

None.

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

``` { .normalize-space .lang-json}
   {
    "response_map": {
      "date": "...",
      "organization": "...",
      "top_tasks": [ ... ],
      "task_count": ...,
      "daily_call_used": ...,
      "daily_call_available": ...
    },
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|`date`|string|The date when the statistics were collected. Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`organization`|string|The name of the SnapLogic Org.|
|`top_tasks`|array|An array of objects containing metadata about ???|
|`task_count`|integer|The number of Task runs that were executed in the current day.|
|`daily_call_used`|integer|The number of Task runs that were executed in the current day.|
|`daily_call_available`|integer|The difference between the daily limit for Task runs and the number of Task runs that were already executed during the day.|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[GET /runtime/\{org\}](../public-apis/get-runtime-org.md)

[GET /runtime/\{org\}/\{ruuid\}](../public-apis/get-runtime-org-ruuid.md)

[GET /runtime/api-stats/\{org\}](../public-apis/get-runtime-apistats-org.md)

[GET /runtime/api-stats/\{org\}/concurrent](../public-apis/get-runtime-apistats-org-concurrent.md)

[POST /runtime/start/\{org\}/\{ruuid\}](../public-apis/post-runtime-start-org-ruuid.md)

[POST /runtime/stop/\{org\}/\{ruuid\}](../public-apis/post-runtime-stop-org-ruuid.md)

