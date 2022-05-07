# PATCH /groups/\{org\}/\{groupname\} {#patch-groups-org-group .concept}

adds or removes users from the specified group.

## Overview { .section}

This API adds or removes users from the specified group.

**Tip:** You can add an existing user to an Org by adding the user to the `members` group of the Org.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   PATCH https://\{pod\_path\}/api/1/rest/public/groups/\{org\}/\{groupname\}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`org`|**Required.** The name of the SnapLogic Org.|
|`groupname`|**Required.** The name of the group.|

Query Parameters

None.

Request Header

Specify Basic Auth for authorization.

``` {#d73e705 .normalize-space}
   Authorization: Basic {your_encoded_security_credentials}

```

Request Body

**Important:** Only one of the following parameters can be used in each API call.

``` {#request-body .normalize-space .lang-json}
   {
    "add_user" : "...",
    "remove_user" : "...",
  }

```

|Key|Type|Description|
|---|----|-----------|
|`add_user`|string|The email address of the user to add to the group.|
|`remove_user`|string|The email address of the user to remove from the group.|

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

[PUT /users/\{email\}](../public-apis/put-users-email.md)

[DELETE /users/\{email\}](../public-apis/delete-users-email.md)

[POST /groups](../public-apis/post-groups.md)

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[GET /groups/\{org\}/\{groupname\}](../public-apis/get-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

