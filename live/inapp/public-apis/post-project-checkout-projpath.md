# POST /project/checkout/\{project\_path\} {#post-project-checkout-projpath .concept}

checks out the specified GitHub branch for the specified project.

## Overview { .section}

This API checks out the specified GitHub branch for the specified project. Equivalent to `git checkout`.

You can use GitHub APIs in Continuous Integration / Continuous Deployment \(CI/CD\) workflows to pull files from GitHub repositories. You can use this API to update a project to a newly tagged version or to revert to a previously stable tag.

**Note:**

-   Your project must already exist.
-   You must use the SnapLogic Manager UI for the initial checkout.

## Prerequisites { .section}

-   Write access to the assets to be added or updated

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/project/checkout/\{project\_path\}

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
   { "ref" : "git\_repository/branch\_name" }

```

|Key|Type|Description|
|---|----|-----------|
|`ref`|string|**Required.** The Git branch to check out. Format: `git_repository/branch_name`

|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

None.

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /project/pull/\{project\_path\}](../public-apis/post-project-pull-projpath.md)

[POST /ghwebhook](../public-apis/post-ghwebhook.md)

[GET /repo-status/\{project\_path\}](../public-apis/get-repo-status-projpath.md)

[SnapLogic GitHub Integration](https://mysnaplogic.atlassian.net/wiki/spaces/SPD/pages/598409895/GitHub+Integration+--+Alpha+Doc+Version)

[GitHub Documentation](https://guides.github.com/)

