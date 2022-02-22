# DELETE /users/\{email\} {#delete-users-email .concept}

deletes the user record associated with the specified email address.

## Overview { .section}

This API deletes the user record associated with the specified email address.

**Warning:** This action permanently removes the user from the SnapLogic system. \(The SnapLogic UI deletes the user from the Org only, not from the system\). To check if the user belongs to other Orgs \(before deletion\), use [PATCH /groups/\{org\}/\{groupname\}](patch-groups-org-group.md).

## Prerequisites { .section}

-   Org Admin permissions for all Orgs that the user belongs to

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   DELETE https://\{pod\_path\}/api/1/rest/public/users/\{email\}

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

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /users](../public-apis/post-users.md)

[GET /users/\{email\}](../public-apis/get-users-email.md)

[PUT /users/\{email\}](../public-apis/put-users-email.md)

[POST /groups](../public-apis/post-groups.md)

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[GET /groups/\{org\}/\{groupname\}](../public-apis/get-groups-org-group.md)

[PATCH /groups/\{org\}/\{groupname\}](../public-apis/patch-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

