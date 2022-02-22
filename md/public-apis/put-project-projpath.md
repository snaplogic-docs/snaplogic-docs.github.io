# PUT /project/\{project\_or\_space\_path\} {#put-project-projpath .concept}

renames an existing project or project space.

## Overview { .section}

This API renames an existing project or project space.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   PUT https://\{pod\_path\}/api/1/rest/public/project/\{project\_or\_space\_path\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`project_or_space_path`|**Required.** The path to the SnapLogic project or project space. Format:

-   Project: `/{org}/{project_space}/{project_name}`
-   Project space: `/{org}/{project_space}`

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
    "name" : "..."
  }

```

|Key|Type|Description|
|---|----|-----------|
|`name`|string|The new name for the project.|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /project/\{project\_or\_space\_path\}](../public-apis/post-project-projpath.md)

