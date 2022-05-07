# POST /project/\{project\_or\_space\_path\} {#post-project-projpath .concept}

creates a new project or project space at the specified path with the specified permissions.

## Overview { .section}

This API creates a new project or project space at the specified path with the specified permissions.

The creator of the project or project space is automatically assigned admin privileges. To assign admin privileges to other users, use one of the following APIs to add them to the `admins` group:

-   `PATCH /groups/{org}/{groupname}`
-   `PUT /groups/{org}/{groupname}`

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/project/\{project\_or\_space\_path\}

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
    "permissions":[
      {
        "perms": [ ... ],
        "inherit": ...,
        "subject_type": "...",
        "subject": "..."
      }
    ]
  }

```

|Key|Type|Description|
|---|----|-----------|
|`perms`|array|An array containing one or more of the following permissions: -   `"R"` – read
-   `"W"` – write
-   `"X"` – execute

 Learn more: [Permissions in Manager and in APIs](../common/../public-apis/api-perms-vs-manager-perms.md)

|
|`inherit`|Boolean|If `true`, the permissions apply to all assets under the specified project path.|
|`subject_type`|string|The type of the `subject`. Valid values:

-   `USER`
-   `GROUP`

|
|`subject`|string|The user or group who can access the new project or project space.|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[PUT /project/\{project\_or\_space\_path\}](../public-apis/put-project-projpath.md)

