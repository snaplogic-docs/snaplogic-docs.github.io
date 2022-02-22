# POST /snaplex/restart/\{plex\_path\}/\{hostname\} {#post-snaplex-restart-plexpath-hostname .concept}

requests a restart of the specified JCC node.

## Overview { .section}

This API requests a restart of the specified JCC node.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/snaplex/restart/\{plex\_path\}/\{hostname\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`plex_path`|**Required.** The path to the Snaplex. Format: `/{org}/{project_space}/{project_name}/{snaplex_name}`

 Example: `/snaplogic/shared/My%20Cloud`

|
|`hostname`|**Required.** The JCC node path. Example: `canxl-jcc8.clouddev.snaplogic.com,canxl-jcc9.clouddev.snaplogic.com`

|

Query Parameters

None.

Request Header

Specify Basic Auth for authorization.

``` {#d73e705 .normalize-space}
   Authorization: Basic {your_encoded_security_credentials}

```

Request Body

``` {#request-body .normalize-space .lang-json}
   {
    "msg" : "...",
    "force" : ...
  }

```

|Key|Type|Description|
|---|----|-----------|
|`msg`|string|The reason for the restart.|
|`force`|Boolean|If `true`, restarts the JCC node immediately. Otherwise, waits for other executions to complete, if any, or for the Snaplex's maximum waiting time.|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /snaplex/maintenance/\{plex\_path\}/\{hostname\}](../public-apis/post-snaplex-maintenance-plexpath-hostname.md)

[GET /snaplex/config/\{plex\_path\}](../public-apis/get-snaplex-config-plexpath.md)

