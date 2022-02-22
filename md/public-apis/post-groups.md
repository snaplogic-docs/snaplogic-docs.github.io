# POST /groups {#post-groups .concept}

creates a group.

## Overview { .section}

This API creates a group.

To create the group and add its members,

1.  Verify that the target Org exists.
2.  Create the group using this API.
3.  Add the members to the group using this API.

**Important:** Avoid space characters in your Group name; instead, use underscores.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   POST https://\{pod\_path\}/api/1/rest/public/groups

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
    "organization" : "...",
    "name" : "...",
    "members" : [ ... ]
  }

```

|Key|Type|Description|
|---|----|-----------|
|`organization`|string|The Org to create the group in.|
|`name`|**Required.** The name of the group.|
|`members`|array|An array of strings containing email addresses of users to add to the group.|

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

[GET /groups/\{org\}](../public-apis/get-groups-org.md)

[GET /groups/\{org\}/\{groupname\}](../public-apis/get-groups-org-group.md)

[PATCH /groups/\{org\}/\{groupname\}](../public-apis/patch-groups-org-group.md)

[PUT /groups/\{org\}/\{groupname\}](../public-apis/put-groups-org-group.md)

[DELETE /groups/\{org\}/\{groupname\}](../public-apis/delete-groups-org-group.md)

