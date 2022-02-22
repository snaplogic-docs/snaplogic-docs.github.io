# GET /runtime/api-stats/\{org\}/concurrent {#get-runtime-apistats-org-concurrent .concept}

retrieves the concurrent metrics of Tasks running at the specified time.

## Overview { .section}

This API retrieves the concurrent metrics of Tasks running at the specified time.

## Prerequisites { .section}

-   Read access to the assets requested

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/runtime/api-stats/\{org\}/concurrent?{query_parameters}

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
|`date_time`|string|The time in UTC format. Default: The current time.

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
      "organization": "...",
      "time_stamp": "...",
      "concurrent_call_in_progress": ...,
      "tasks": [ ... ]
    },
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|`organization`|string|The name of the SnapLogic Org.|
|`time_stamp`|string|The timestamp when the statistics were collected. Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`concurrent_call_in_progress`|integer|The number of Task runs that are concurrently in progress.|
|`tasks`|array|An array of objects containing metadata about each Task run.|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[GET /runtime/\{org\}](../public-apis/get-runtime-org.md)

[GET /runtime/\{org\}/\{ruuid\}](../public-apis/get-runtime-org-ruuid.md)

[GET /runtime/api-stats/\{org\}](../public-apis/get-runtime-apistats-org.md)

[GET /runtime/api-stats/\{org\}/daily](../public-apis/get-runtime-apistats-org-daily.md)

[POST /runtime/start/\{org\}/\{ruuid\}](../public-apis/post-runtime-start-org-ruuid.md)

[POST /runtime/stop/\{org\}/\{ruuid\}](../public-apis/post-runtime-stop-org-ruuid.md)

