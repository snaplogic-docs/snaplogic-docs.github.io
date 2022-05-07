# GET /snaplex/\{org\} {#get-snaplex-org .concept}

retrieves Snaplex and JCC wrapper information about all nodes or about the node, specified by the Snaplex path or the hostname.

## Overview { .section}

This API retrieves Snaplex and JCC wrapper information about all nodes or about the node, specified by the Snaplex path or the hostname.

-   If called without parameters, the API returns information about all the nodes in the Org.
-   If plex\_path or hostname is specified, the API returns information about the specified nodes only.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/snaplex/\{org\}?{query_parameters}

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
|`plex_path`|string|The path to the Snaplex. Format: `/{org}/{project_space}/{project_name}/{snaplex_name}`

|
|`hostname`|string|**Required.** A single JCC node path or a comma-separated list of JCC node paths. Example:`canxl-jcc8.clouddev.snaplogic.com,canxl-jcc9.clouddev.snaplogic.com`

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

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

