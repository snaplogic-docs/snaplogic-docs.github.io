# GET /snaplex/version/latest {#get-snaplex-version-latest .concept}

determines the latest active version of the Snaplex package.

## Overview { .section}

This API determines the latest active version of the Snaplex package.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/snaplex/version/latest

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|

Query Parameters

None.

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
        "version": "...",
        "comment": "...",
        "status": "..."
    },
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|`version`|string|The latest active version of the Snaplex.|
|`comment`|string|A description of the Snaplex version.|
|`status`|string|The status of the Snaplex version. Possible values:

-   active
-   deprecated

|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /snaplex/version/\{plex\_path\}](../public-apis/post-snaplex-version-plexpath.md)

[POST /snaplex/version/latest/\{plex\_path\}](../public-apis/post-snaplex-version-latest-plexpath.md)

[GET /snaplex/version](../public-apis/get-snaplex-version.md)

