# GET /snaplex/version {#get-snaplex-version .concept}

retrieves information about all versions of the Snaplex packages.

## Overview { .section}

This API retrieves information about all versions of the Snaplex packages.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/snaplex/version

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
    "response_map": [
      {
        "version": "...",
        "comment": "...",
        "status": "..."
      },
      ...
    ],
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|`version`|string|The Snaplex version.|
|`comment`|string|A description of the Snaplex version.|
|`status`|string|The status of the Snaplex version. Possible values:

-   active
-   deprecated

|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /snaplex/version/\{plex\_path\}](../public-apis/post-snaplex-version-plexpath.md)

[POST /snaplex/version/latest/\{plex\_path\}](../public-apis/post-snaplex-version-latest-plexpath.md)

[GET /snaplex/version/latest](../public-apis/get-snaplex-version-latest.md)

