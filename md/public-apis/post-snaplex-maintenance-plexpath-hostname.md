# POST /snaplex/maintenance/\{plex\_path\}/\{hostname\} {#post-snaplex-maintenance-plexpath-hostname .concept}

requests putting the specified JCC node into maintenance mode.

## Overview { .section}

This API requests putting the specified JCC node into maintenance mode.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/snaplex/maintenance/\{plex\_path\}/\{hostname\}

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
   { "mode" : ... }

```

|Key|Type|Description|
|---|----|-----------|
|`mode`|Boolean|If `true`, the JCC node is set to maintenance mode. Otherwise, the JCC node is set to running mode.|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

``` {#response-body .normalize-space .lang-json}
 
```

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /snaplex/restart/\{plex\_path\}/\{hostname\}](../public-apis/post-snaplex-restart-plexpath-hostname.md)

[GET /snaplex/config/\{plex\_path\}](../public-apis/get-snaplex-config-plexpath.md)

