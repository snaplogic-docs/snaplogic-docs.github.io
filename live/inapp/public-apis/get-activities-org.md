# GET /activities/\{org\} {#get-activities-org .concept}

retrieves information about activities performed within an organization.

## Overview { .section}

This API retrieves information about activities performed within an organization.

You can filter the results based on one or more of the following criteria:

-   project space
-   project
-   asset
-   asset\_type
-   user
-   event\_type
-   alert\_state
-   is\_alert
-   start
-   end
-   offset
-   limit

## Prerequisites { .section}

-   Read access to the assets requested

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/activities/\{org\}?{query_parameters}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`org`|**Required.** The name of the SnapLogic Org.|

Query Parameters

|Key|Type|Description|
|---|----|-----------|
|`filter_project_space`|string|Returns activities related to a project space.|
|`filter_project`|string|Returns activities related to a project. Requires `filter_project_space`. Example: `filter_project_space=myProjSpace&filter_project=My%20Test%20Project`

|
|`filter_asset`|string|Returns activities related to the specified asset. Requires `filter_project_space` and `filter_ project`. Example: `filter_asset_type=File&filter_asset=Sales2021Dec.csv`

|
|`filter_asset_type`|string|Returns activities related to specific type of assets. Valid values:

-   `Account`
-   `File`
-   `Org`
-   `Pipeline`
-   `Plex`

 Example: `filter_asset_type=File`

|
|`filter_user`|string|Returns activities related to a user.|
|`filter_event_type`|CSV string|Returns activities of a one or more event types separated by comma.|
|`filter_alert_state`|string|Returns activities that match the specified alert state. Valid values:

-   `open` indicates that a potential issue in the activity must be investigated.
-   `closed` indicates that an issue occurred in the activity and has been automatically resolved.

|
|`filter_is_alert`|Boolean|If `true`, returns activities that are alerts; otherwise, returns activities that are not alerts.|
|`filter_snaplogic_admin_update`|Boolean|If `true`, returns activities that were initiated by a SnapLogic process.|
|`start`|integer|Returns activities that occurred since the specified timestamp. Time must be provided as Unix time in milliseconds.|
|`end`|integer|Returns activities that occurred before the specified timestamp. Time must be provided as Unix time in milliseconds.|
|`limit`|integer|Returns no more than the specified number of results. You can use `limit` and `offset` for pagination. Valid values: 1 to 100,000

 Default: 100

|
|`offset`|integer|Returns a subset of the results starting at this 0-based index. You can use `limit` and `offset` for pagination. Default: 0

|

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

``` {#response-body .normalize-space .lang-json}
   {
    "total": ...,
    "offset": ...,
    "limit": ...,
    "entries": [ ... ]
  }

```

|Key|Type|Description|
|---|----|-----------|
|`total`|integer|The total number of results available.|
|`offset`|integer|The index of the first result returned.|
|`limit`|integer|The number of results returned.|
|`entries`|array|An array of objects containing metadata about each activity. The structure of each object depends on the event type. Learn more: [Reference: Activity Metadata](ref-activity-metadata.md)

|

The activity logs capture the following events:

-   session\_start
-   session\_end
-   user\_create
-   user\_delete
-   user\_auth\_failure
-   user\_lockout
-   user\_unlock
-   password\_change
-   password\_reset
-   asset\_create
-   asset\_update
-   asset\_delete
-   asset\_rename
-   asset\_owner\_change
-   asset\_move
-   acl\_add
-   acl\_remove
-   plex\_node\_add
-   plex\_node\_restart
-   dist\_change
-   dist\_override
-   group\_create
-   group\_delete
-   group\_update
-   plex\_congestion
-   plex\_node\_enter\_maintenance\_mode
-   plex\_node\_leave\_maintenance\_mode

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[Activity Log](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1438857/Activity+Log)

