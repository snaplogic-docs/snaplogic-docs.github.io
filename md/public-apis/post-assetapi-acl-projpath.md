# POST /assetapi/acl/\{project\_path\} {#post-assetapi-acl-projpath .concept}

grants a user or group access to the specified project.

## Overview { .section}

This API grants a user or group access to the specified project.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/assetapi/acl/\{project\_path\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`project_path`|**Required.** The path to the SnapLogic project. Format: `/{org}/{project_space}/{project_name}`

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
    "grant_type" : "...",
    "grantee" : "...",
    "permission_list" : [ ... ],
    "inherit" : true
  }

```

|Key|Type|Description|
|---|----|-----------|
|`grant_type`|string|The type of the `grantee`. Valid values:

-   `USER`
-   `GROUP`

|
|`grantee`|string|The user or group to whom to grant access.|
|`permission_list`|array|An array containing one or more of the following permissions: -   `"R"` – read
-   `"W"` – write
-   `"X"` – execute

 Learn more: [Permissions in Manager and in APIs](../common/../public-apis/api-perms-vs-manager-perms.md)

|
|`inherit`|Boolean|If `true`, the permissions apply to all assets under the specified project path.|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[GET /assetapi/acl/\{project\_path\}](../public-apis/get-assetapi-acl-projpath.md)

[DELETE /assetapi/acl/\{project\_path\}](../public-apis/delete-assetapi-acl-projpath.md)

