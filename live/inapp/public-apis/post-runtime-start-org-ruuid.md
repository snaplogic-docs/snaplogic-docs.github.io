# POST /runtime/start/\{org\}/\{ruuid\} {#post-runtime-start-org-ruuid .concept}

resumes the Resumable Task with the specified Runtime ID.

## Overview { .section}

This API resumes the Resumable Task with the specified Runtime ID.

## Prerequisites { .section}

-   Write access to the assets to be added or updated

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/runtime/start/\{org\}/\{ruuid\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`org`|**Required.** The name of the SnapLogic Org.|
|`ruuid`|**Required.** The Runtime ID of the Pipeline. To get the Runtime ID of a running Pipeline:

1.  Go to **Dashboard** \> **Pipeline**.
2.  In the **Executing Pipelines of All Projects** list, click the Pipeline you want.
3.  From the address bar of the web browser tab that displays the Pipeline, copy the value of the parameter `pipe_runtime_id`.

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


[GET /runtime/\{org\}](../public-apis/get-runtime-org.md)

[GET /runtime/\{org\}/\{ruuid\}](../public-apis/get-runtime-org-ruuid.md)

[GET /runtime/api-stats/\{org\}](../public-apis/get-runtime-apistats-org.md)

[GET /runtime/api-stats/\{org\}/daily](../public-apis/get-runtime-apistats-org-daily.md)

[GET /runtime/api-stats/\{org\}/concurrent](../public-apis/get-runtime-apistats-org-concurrent.md)

[POST /runtime/stop/\{org\}/\{ruuid\}](../public-apis/post-runtime-stop-org-ruuid.md)

