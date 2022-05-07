# POST /ghwebhook {#post-ghwebhook .concept}

creates a GitHub webhook that subscribes to events on GitHub.com.

## Overview { .section}

This API creates a GitHub webhook that subscribes to events on GitHub.com.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/ghwebhook

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

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /project/checkout/\{project\_path\}](../public-apis/post-project-checkout-projpath.md)

[POST /project/pull/\{project\_path\}](../public-apis/post-project-pull-projpath.md)

[GET /repo-status/\{project\_path\}](../public-apis/get-repo-status-projpath.md)

[GitHub Docs: About webhooks](https://docs.github.com/en/developers/webhooks-and-events/webhooks/about-webhooks)

