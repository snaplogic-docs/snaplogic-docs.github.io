# PUT /users/\{email\} {#put-users-email .concept}

updates the user record associated with the specified email address.

## Overview { .section}

This API updates the user record associated with the specified email address.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   PUT https://\{pod\_path\}/api/1/rest/public/users/\{email\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`email`|**Required.** The email address of the user.|

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
    "first_name" : "...",
    "last_name" : "...",
    "allow_password_login" : ...,
    "revoke_old_password" : ...,
    "utility" : ...,
    "ui_access" : ...,
    "created_by" : "...",
    "certificate" : "...",
    "file_handle" : "..."
  }

```

|Key|Type|Description|
|---|----|-----------|
|`first_name`|string|The first name of the user.|
|`last_name`|string|The last name of the user.|
|`allow_password_login`|Boolean|If `true`, the user is allowed to log in with a password. Otherwise, ???.|
|`revoke_old_password`|Boolean|If `true`, the user's password is invalidated. ???|
|`utility`|Boolean|If `true`, the account is tagged as a service account, not a user account, for use with automated processes. ???|
|`ui_access`|Boolean|If `true`, the user is granted access to the SnapLogic UI.|
|`created_by`|string|The user who originally created the account, if it is a service account. Learn more: [Creating a User](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1439028)

|
|`certificate`|string|???|
|`file_handle`|string|???|

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /users](../public-apis/post-users.md)

[GET /users/\{email\}](../public-apis/get-users-email.md)

[DELETE /users/\{email\}](../public-apis/delete-users-email.md)

[POST /groups](../public-apis/post-groups.md)

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[GET /groups/\{org\}/\{groupname\}](../public-apis/get-groups-org-group.md)

[PATCH /groups/\{org\}/\{groupname\}](../public-apis/patch-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

