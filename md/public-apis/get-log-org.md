# GET /log/\{org\} {#get-log-org .concept}

retrieves the Pipeline log information for the specified Org.

## Overview { .section}

This API retrieves the Pipeline log information for the specified Org.

## Prerequisites { .section}

-   Read access to the assets requested

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/log/\{org\}?{query_parameters}

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
|`ruuid`|string|**Required.** Returns log information about the task with the specified runtime ID.|
|`log_level`|string|Returns log information at the specified level of detail. Valid values:

-   `error` – Returns error logs only.
-   `warn` – Returns both warning logs and error logs.
-   `info` – Returns all logged information, including warning logs and error logs.

 Default: `info`

|
|`limit`|integer|Returns no more than the specified number of results. You can use `limit` and `offset` for pagination. Valid values: 1 to 100,000

 Default: 100

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
      "extra": {},
      "total": ...,
      "entries": [
        {
          "_source": {
            "msg": "...",
            "lvl": "...",
            "ts": "...",
            "prc": "...",
            "fi": "..."
          }
        },
        ...
        {
          "_source": {
            "xid": "...",
            "snrd": "...",
            "prc": "...",
            "linid": "...",
            "ts": "...",
            "plrd": "...",
            "fi": "...",
            "msg": "...",
            "lvl": "...",
            "snlb": "...",
            "exc": "..."
          }
        }
      ]
    },
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|`extra`|object|???|
|`total`|integer|The number of log entries returned.|
|`entries`|array|An array of objects containing metadata about each log entry. -   `msg`. The message in the log.
-   `lvl`. The type of the log entry. Possible values:
    -   `INFO`
    -   `WARN`
    -   `ERROR`
-   `ts`. The timestamp of the entry. Format: UTC
-   `prc`. The process that was logged.
-   `fi`. The line in the code that generated the log entry.

 If `lvl` is `ERROR`:

 -   `xid`. The transaction ID.
-   `snrd`. The Snap runtime ID.
-   `linid`. ???
-   `plrd`. The Pipeline runtime ID.
-   `snlb`. The Snap label or name.
-   `exc`. Any exception that occurred.

|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

