# GET /snaplex/config/\{plex\_path\} {#get-snaplex-config-plexpath .concept}

retrieves the information needed to install and configure a node on a Groundplex.

## Overview { .section}

This API retrieves the information needed to install and configure a node on a Groundplex.

You can use this API to automate the installation of Groundplex nodes.

## Prerequisites { .section}

-   Org Admin permissions

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/snaplex/config/\{plex\_path\}?{query_parameters}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`plex_path`|**Required.** The path to the Snaplex. Format: `/{org}/{project_space}/{project_name}/{snaplex_name}`

 Example: `/snaplogic/shared/My%20Cloud`

|

Query Parameters

|Key|Type|Description|
|---|----|-----------|
|`expire_hours`|integer|The number of hours before the returned URL expires. The URL is a link to the Snaplex configuration file. ??? Valid range: 1 to ??? hours

 Default: 1 hour

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

``` { .normalize-space .lang-json}
   {
    "response_map": {
      "config": "...",
      "pkgs": {
        "plex-rpm": {
          "comment": "...",
          "status": "...",
          "kind": "plex-rpm",
          "signatures": {
            "md5": "..."
          },
          "pkg_file": "...",
          "driver": ...,
          "uri": "...",
          "version": "...",
          "compatible_version": "...",
          "create_time": "...",
          "_id": "..."
        },
        "plex-deb": {
          ...
        },
        "plex-win": {
          ...
        }
      }
    },
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|config|string|The signed URL where you can download the configuration file \(`.slpropz`\) for the Snaplex node. **Note:** If you are an Org administrator, the configuration file contains generic credentials for the Snaplex node. Otherwise, the configuration file contains the caller's credentials.

|
|pkgs|object|The Snaplex software packages that are available for installation. The following metadata is included for each package type:

-   `comment` – A description of the Snaplex package.
-   `status` – The status of the Snaplex version.

Possible values:

    -   active
    -   deprecated
-   `kind` – The type of the Snaplex package.

Available types:

    -   `plex-rpm`
    -   `plex-deb`
    -   `plex-win`
-   `signatures` – Key-value pairs where the keys represent the hash algorithm and the values contain the hashed signatures that are used for ???.

Possible keys:

    -   `md5`
    -   ???
-   `pkg_file` – The zip file that contains the installation files.
-   `driver` – ???
-   `uri` – The URI where you can download the Snaplex package.
-   `version` – The SnapLogic version included in the zip file. ???
-   `compatible_version` – SnapLogic versions that the package is compatible with. ???
-   `create_time` – The time that the zip file was created. ???

Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

-   `_id` – The ID of the Snaplex package. ???

|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[POST /snaplex/restart/\{plex\_path\}/\{hostname\}](../public-apis/post-snaplex-restart-plexpath-hostname.md)

[POST /snaplex/maintenance/\{plex\_path\}/\{hostname\}](../public-apis/post-snaplex-maintenance-plexpath-hostname.md)

