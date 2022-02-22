# POST /users {#post-users .concept}

creates a user.

## Overview { .section}

This API creates a user.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/users

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

``` {#request-body .normalize-space .lang-json}
   {
    "email" : "...",
    "first_name" : "...",
    "last_name" : "...",
    "organization" : "...",
    "administrator" : ...,
    "allow_password_login" : ...,
    "utility" : ...,
    "ui_access" : ...,
    "create_home_directory" : ...,
    "email_notification" : ...,
    "certificate" : "...",
    "file_handle" : "..."
  }

```

|Key|Type|Description|
|---|----|-----------|
|`email`|string|The email address of the user.|
|`first_name`|string|The first name of the user.|
|`last_name`|string|The last name of the user.|
|`organization`|string|The Org to assign the user to.|
|`administrator`|Boolean|If `true`, the user is assigned as an Org administrator.|
|`allow_password_login`|Boolean|If `true`, the user is allowed to log in with a password. Otherwise, ???.|
|`utility`|Boolean|If `true`, the account is tagged as a service account, not a user account, for use with automated processes. ???|
|`ui_access`|Boolean|If `true`, the user is granted access to the SnapLogic UI.|
|`create_home_directory`|Boolean|If `true`, a home directory is created for the user.|
|`email_notification`|Boolean|If `true`, the user is sent a welcome email when the account is created.|
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


[GET /users/\{email\}](../public-apis/get-users-email.md)

[PUT /users/\{email\}](../public-apis/put-users-email.md)

[DELETE /users/\{email\}](../public-apis/delete-users-email.md)

[POST /groups](../public-apis/post-groups.md)

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[GET /groups/\{org\}/\{groupname\}](../public-apis/get-groups-org-group.md)

[PATCH /groups/\{org\}/\{groupname\}](../public-apis/patch-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

