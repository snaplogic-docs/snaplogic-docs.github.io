# GET /groups/\{org\}/\{groupname\} {#get-groups-org-group .concept}

retrieves information about the specified group.

## Overview { .section}

This API retrieves information about the specified group.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/groups/\{org\}/\{groupname\}

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

None.

Response Header

|Key|Description|
|---|-----------|
|`X-SL-StatusCode`|Status code indicating the results of the request. Learn more: [HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

|

Response Body

``` { .normalize-space .lang-json}
   {
    "name": "...",
    "members": [ ... ]
  }

```

|Key|Type|Description|
|---|----|-----------|
|`name`|string|The name of the group.|
|`members`|array of strings|The usernames or email addresses of the group members.|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /users](../public-apis/post-users.md)

[GET /users/\{email\}](../public-apis/get-users-email.md)

[PUT /users/\{email\}](../public-apis/put-users-email.md)

[DELETE /users/\{email\}](../public-apis/delete-users-email.md)

[POST /groups](../public-apis/post-groups.md)

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[PATCH /groups/\{org\}/\{groupname\}](../public-apis/patch-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

