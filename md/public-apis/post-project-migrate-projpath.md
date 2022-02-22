# POST /project/migrate/\{project\_path\} {#post-project-migrate-projpath .concept}

migrates a SnapLogic Project from one Org to another.

## Overview { .section}

This API migrates a SnapLogic Project from one Org to another.

## Prerequisites { .section}

-   Read access to the source Project
-   Write access to the target Org

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/project/migrate/\{project\_path\}

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

Specify Basic Auth for authorization and JSON for content type.

``` {#d73e720 .normalize-space}
   Authorization: Basic {your_encoded_security_credentials}
  Content-Type: application/json

```

Request Body

``` {#request-body .normalize-space .lang-json}
   {
    "dest_path" : "...",
    "asset_types" : [ ... ],
    "async" : true,
    "duplicate_check" : true
  }

```

|Key|Type|Description|
|---|----|-----------|
|`dest_path`|string|**Required.** The path to the destination Project.|
|`asset_types`|array of strings|The types of assets to migrate. Valid values:

-   `File`
-   `Job`
-   `Account`
-   `Pipeline`

|
|`async`|Boolean|If `true`, the migration is done asynchronously. A response is immediately returned with `status_token` and `status_url`, which you can use to check on the status of the migration \(Started, Completed, or Failed\).

 Default: `true`

|
|`duplicate_check`|Boolean|If `true`, throws an exception if a project with the same name already exists at the specified path.

 If `false`, overwrites any existing project with the same name at the specified path.

 Default: `true`

|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

``` {#response-body .normalize-space .lang-json}
 
```

Project Migration Guidelines

-   The first migration to the destination Org creates a new Project if there is no conflict. However, the existing Project is overwritten if there is a conflict.
-   When you include previously migrated accounts and Tasks in subsequent migrations, the API overwrites any changes that you may have manually made to the assets after the initial migration.
-   If the account name is changed after the migration, you must update all references to that account in the Pipelines.
-   Every time you migrate a Project, SnapLogic retains existing associations between Pipelines and Tasks if the associated Tasks are included in the migration.

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[GET /migrate/\{status\_token\}](../public-apis/get-migrate-status-token.md)

