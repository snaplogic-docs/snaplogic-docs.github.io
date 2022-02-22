# GET /users/\{email\} {#get-users-email .concept}

retrieves the user record associated with the specified email address.

## Overview { .section}

This API retrieves the user record associated with the specified email address.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/users/\{email\}

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

None.

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

``` { .normalize-space .lang-json}
   {
    "last_name": "...",
    "first_name": "...",
    "password_last_updated": "...",
    "password_expired": ...,
    "allow_password_login": ...,
    "organizations": [
      {
        "administrator": ...,
        "id": "...",
        "name": "..."
      },
      ...
    ],
    "basic_access": "...",
    "ui_access": ...,
    "user_locked_out": ...,
    "service_account": ...,
    "email": "..."
  }

```

|Key|Type|Description|
|---|----|-----------|
|`last_name`|string|The last name of the user.|
|`first_name`|string|The first name of the user.|
|`password_last_updated`|string|When the user's password was last changed. Format: [UTC](https://www.w3.org/TR/NOTE-datetime)|
|`password_expired`|Boolean|If `true`, the user's password is expired.|
|`allow_password_login`|Boolean|If `true`, ???|
|`organizations`|array of objects|The list of Orgs that the user belongs to. Each object contains `name` and `id` of the Org and a Boolean \(`administrator`\) that indicates whether the user is assigned the administrator role in the Org.|
|`basic_access`|string|??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)|
|`ui_access`|Boolean|If `true`, the user can use the SnapLogic UI. ???|
|`user_locked_out`|Boolean|If `true`, the user is denied access to the Snaplex. ???|
|`service_account`|Boolean|If `true`, ???.|
|`email`|string|The user's email address.|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /users](../public-apis/post-users.md)

[PUT /users/\{email\}](../public-apis/put-users-email.md)

[DELETE /users/\{email\}](../public-apis/delete-users-email.md)

[POST /groups](../public-apis/post-groups.md)

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[GET /groups/\{org\}/\{groupname\}](../public-apis/get-groups-org-group.md)

[PATCH /groups/\{org\}/\{groupname\}](../public-apis/patch-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

