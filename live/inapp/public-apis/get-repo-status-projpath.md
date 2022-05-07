# GET /repo-status/\{project\_path\} {#get-repo-status-projpath .concept}

retrieves the status of the Git repository associated with the specified project.

## Overview { .section}

This API retrieves the status of the Git repository associated with the specified project.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/repo-status/\{project\_path\}

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

None.

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /project/checkout/\{project\_path\}](../public-apis/post-project-checkout-projpath.md)

[POST /project/pull/\{project\_path\}](../public-apis/post-project-pull-projpath.md)

[POST /ghwebhook](../public-apis/post-ghwebhook.md)

