# DELETE /assetapi/acl/\{project\_path\} {#delete-assetapi-acl-projpath .concept}

revokes all project access from a user or group.

## Overview { .section}

This API revokes all project access from a user or group.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   DELETE https://\{pod\_path\}/api/1/rest/public/assetapi/acl/\{project\_path\}?{query_parameters}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`project_path`|**Required.** The path to the SnapLogic project. Format: `/{org}/{project_space}/{project_name}`

|

Query Parameters

|Key|Type|Description|
|---|----|-----------|
|`grant_type`|string|The type of the `grantee`. Valid values:

-   `USER`
-   `GROUP`

|
|`grantee`|string|The user or group from whom to revoke access.|

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

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /assetapi/acl/\{project\_path\}](../public-apis/post-assetapi-acl-projpath.md)

[GET /assetapi/acl/\{project\_path\}](../public-apis/get-assetapi-acl-projpath.md)

