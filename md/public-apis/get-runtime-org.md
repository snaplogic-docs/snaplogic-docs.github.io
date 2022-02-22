# GET /runtime/\{org\} {#get-runtime-org .concept}

retrieves information about Task runs that match the specified filters.

## Overview { .section}

This API retrieves information about Task runs that match the specified filters.

## Prerequisites { .section}

-   Read access to the assets requested

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/runtime/\{org\}?{query_parameters}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`org`|**Required.** The name of the SnapLogic Org.|

Query Parameters

**Note:** If a timespan is not set, this API returns information about Task runs within the last hour.

|Key|Type|Description|
|---|----|-----------|
|`plex_label`|string|Returns information about Task runs for the specified Snaplex.|
|`cc_label`|string|Returns information about Task runs for the specified CC label \(JCC node’s hostname\).|
|`pipe_name`|string|Returns information about Task runs for the specified Pipeline.|
|`user_id`|string|Returns information about Task runs triggered by the specified user.|
|`state`|string|Returns information about Task runs in the specified state. Valid values:

-   `Queued` – Task is queued for processing; all Tasks start in this state.
-   `NoUpdate` – Intermediate state at startup.
-   `Prepared` – Task has been prepared.
-   `Started` – Task has started running.
-   `Completed` – Task has completed successfully.
-   `Failing` – Task encountered an error and is waiting for Snaps to complete execution before moving to the Failed state.
-   `Failed` – Task failed.
-   `Stopped` – Task was stopped either by the user or by the system, as indicated by the "stopper" key.
-   `Stopping` – Task is stopping.
-   `Suspending` – Resumable Task encountered an error and is storing its state.
-   `Suspended` – Resumable Task encountered an error and is suspended.
-   `Resuming` – Resumable Task is loading its state and will resume execution where it left off.

 Default: `Started`

|
|`invoker`|string|Returns information about Task runs that were invoked in the specified way. Valid values:

-   `triggered` – Triggered Tasks
-   `scheduled` – Scheduled Tasks
-   `always_on` – Ultra Tasks
-   `manual` – User-triggered Tasks

 Default: `scheduled`

|
|`project_path`|string|Returns information about Task runs for the specified project. Allowed formats:

-   `/{org}/projects/{project_name}`
-   `/{org}/shared`

|
|`last_hours`|integer|Returns information about Task runs within the specified number of hours, counting backwards from the current time. Valid values: 1 to 1080 hours \(45 days\)

 Default: 1

|
|`start`|integer|Returns information about Task runs since the specified time. Time must be provided as Unix time in milliseconds.|
|`end`|integer|Returns information about Task runs before the specified time. Time must be provided as Unix time in milliseconds.|
|`limit`|integer|Returns no more than the specified number of results. You can use `limit` and `offset` for pagination. Valid values: 1 to 1,000 ???

 Default: 10

|
|`offset`|integer|Returns a subset of the results starting at this 0-based index. You can use `limit` and `offset` for pagination. Default: 0

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
    "entries": [ ... ],
    "total": ...,
    "limit": ...,
    "offset": ...
  },
  "http_status_code": 200
}

```

|Key|Type|Description|
|---|----|-----------|
|`entries`|array|An array of objects containing metadata about each Task run.|
|`total`|integer|The total number of results available.|
|`limit`|integer|The number of results returned.|
|`offset`|integer|The index of the first result returned.|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[GET /runtime/\{org\}/\{ruuid\}](../public-apis/get-runtime-org-ruuid.md)

[GET /runtime/api-stats/\{org\}](../public-apis/get-runtime-apistats-org.md)

[GET /runtime/api-stats/\{org\}/daily](../public-apis/get-runtime-apistats-org-daily.md)

[GET /runtime/api-stats/\{org\}/concurrent](../public-apis/get-runtime-apistats-org-concurrent.md)

[POST /runtime/start/\{org\}/\{ruuid\}](../public-apis/post-runtime-start-org-ruuid.md)

[POST /runtime/stop/\{org\}/\{ruuid\}](../public-apis/post-runtime-stop-org-ruuid.md)

