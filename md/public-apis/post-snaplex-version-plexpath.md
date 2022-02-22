# POST /snaplex/version/\{plex\_path\} {#post-snaplex-version-plexpath .concept}

updates the Snaplex to the specified version.

## Overview { .section}

This API updates the Snaplex to the specified version.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/snaplex/version/\{plex\_path\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`plex_path`|**Required.** The path to the Snaplex. Format: `/{org}/{project_space}/{project_name}/{snaplex_name}`

 Example: `/snaplogic/shared/My%20Cloud`

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
   { "version" : "..." }

```

|Key|Type|Description|
|---|----|-----------|
|`version`|string|The version to upgrade to.|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /snaplex/version/latest/\{plex\_path\}](../public-apis/post-snaplex-version-latest-plexpath.md)

[GET /snaplex/version](../public-apis/get-snaplex-version.md)

[GET /snaplex/version/latest](../public-apis/get-snaplex-version-latest.md)

