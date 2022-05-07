# GET /runtime/\{org\}/\{ruuid\} {#get-runtime-org-ruuid .concept}

retrieves information about the Task run with the specified Runtime ID.

## Overview { .section}

This API retrieves information about the Task run with the specified Runtime ID.

## Prerequisites { .section}

-   Read access to the assets requested

-   Request
-   Response
-   Notes
-   Examples

``` {#codeblock-endpoint .normalize-space .lang-uri}
   GET https://\{pod\_path\}/api/1/rest/public/runtime/\{org\}/\{ruuid\}?{query_parameters}

```

Path Parameters

|Key|Description|
|---|-----------|
|`pod_path`|**Required.** The path to your SnapLogic pod. Example: `elastic.snaplogic.com`

|
|`org`|**Required.** The name of the SnapLogic Org.|
|`ruuid`|**Required.** The Runtime ID of the Pipeline. To get the Runtime ID of a running Pipeline:

1.  Go to **Dashboard** \> **Pipeline**.
2.  In the **Executing Pipelines of All Projects** list, click the Pipeline you want.
3.  From the address bar of the web browser tab that displays the Pipeline, copy the value of the parameter `pipe_runtime_id`.

|

Query Parameters

|Key|Type|Description|
|---|----|-----------|
|`level`|string|Returns Task run information at the specified level of detail. Valid values:

-   `Summary` – Returns less detailed information.
-   `Detail` – Returns more detailed information.

 Default: `Summary`

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
      "feed_call": ...,
      "subpipeline_parameters": { ... },
      "llfeed_status": {
        "message_history": [ ... ],
        "messages": [ ... ],
        "documents_count": ...,
        "max_in_flight": ...,
        "summary": "..."
      },
      "class_fqid": "...",
      "snode_id": "...",
      "ttl": ...,
      "org_snode_id": "...",
      "cc_prepare_end_ms": ...,
      "parent_path": "...",
      "error_list": [ ... ],
      "child_count": ...,
      "data_locations": [ ... ],
      "env_map": { ... },
      "restart_attempts": ...,
      "error_documents_count": ...,
      "env_map_list": [
        {
          "ciphertext": "...",
          "sym_key": {
            "alias": "...",
            "key": "..."
          }
        }
      ],
      "statistics_time_stamp": "...",
      "job_trigger": "...",
      "cc_fast_push_expire_time_ms": ...,
      "fault_injections": ...,
      "slserver_lease_expire_time": "...",
      "cc_poll_ms": ...,
      "instance_id": "...",
      "mode": "...",
      "async": ...,
      "pipe_invoker": "...",
      "create_time": "...",
      "duration": ...,
      "notification": {
        "slack_recipients": [
          {
            "user": [ ... ],
            "channel": [ ... ]
          }
        ]
      },
      "label": "...",
      "state": "...",
      "replicaset_label": "...",
      "invoker": "...",
      "cc_user": "...",
      "time_stamp": "...",
      "cc_external_uri": "...",
      "partition_snode_id": "...",
      "lint_id_list": [ ... ],
      "reason": "...",
      "threads": [ ... ],
      "prepare_handoff_timestamp": "...",
      "slot_count": ...,
      "end_stage": "...",
      "search": "...",
      "limits": "...",
      "class_id": "...",
      "has_lints": ...,
      "q_threshold_time": "...",
      "control_plane_scheduling": [
        {
          "update_buckets": { ... },
          "leases": { ... },
          "stats": {
            "active_pipelines": [ ... ],
            "cpu_user": ...,
            "mem_used": ...,
            "active_threads": ...,
            "open_file_descriptors": ...,
            "system_load_average": ...
          },
          "generation": ...,
          "slots_in_use": ...,
          "time_stamp": "...",
          "_id": "..."
        }
      ],
      "suggest_uris": "...",
      "task_status": [ ... ],
      "cc_prepare_start_ms": ...,
      "phase_snode_id": "...",
      "duration_ms": ...,
      "parent_ruuid": "...",
      "references": [
        {
          "path": "...",
          "pipe_origin": "...",
          "time_updated": "...",
          "asset_type": "...",
          "snode_id": "..."
        }
      ],
      "do_start": ...,
      "statistics": {
        "output_views": { ... },
        "input_views": { ... }
      },
      "user_id": "...",
      "connect_pipeline_views": ...,
      "container_type": "...",
      "priority": ...,
      "instance_fqid": "...",
      "info_flag_list": [ ... ],
      "runtime_path_id": "...",
      "lint_list": [ ... ],
      "failure": "...",
      "state_log": [
        {
          "timestamp": ...,
          "ccid": "...",
          "new_state": "NoUpdate"
        },
        {
          "timestamp": ...,
          "new_state": "Prepared"
        },
        {
          "timestamp": ...,
          "new_state": "Started"
        }
      ],
      "ruuid": "...",
      "parent_pipeline_fqid": "...",
      "execution_timeout": "...",
      "path_id": "...",
      "plex_snode_id": "...",
      "error": { ... },
      "plex_path": "...",
      "invoker_snode_id": "...",
      "invoker_path_id": "...",
      "snaplex_label": "...",
      "platform_globals": {
        "task": {
          "start": {
            "_snaptype_datetime": "..."
          },
          "end": {
            "_snaptype_datetime": "..."
          }
        }
      },
      "init_xid": "...",
      "nested_pipeline": ...,
      "project_snode_id": "...",
      "class_version": ...,
      "warning_list": [ ... ],
      "root_ruuid": "...",
      "cc_start_ms": ...,
      "poll_time_stamp": "...",
      "artifacts_map": {
        "...": "..."
      },
      "artifact_snap_id_map": {
        "...": "..."
      },
      "ccid": "...",
      "delivery_options": { ... },
      "metrics": {
        "queuedCount": ...,
        "totalSnapDelay": ...,
        "idleTime": ...,
        "memoryOverhead": ...,
        "inFlightCount": ...,
        "startTime": ...
      },
      "expire_time": "...",
      "runtime_label": "...",
      "cc_stop_ms": ...,
      "root_path": "...",
      "invoker_name": "...",
      "error_fp_list": [ ... ],
      "flags": {
        "immediate_mode": ...,
        "is_suggest": ...,
        "connect_views_to_relay": ...
      },
      "captured_env_map": {
        "key1": {
          "captured": ...,
          "value": "..."
        }
      },
      "llfeed_context": {
        "path_id": "...",
        "job_alias": "...",
        "masters": [
          {
            "uri": "...",
            "certificate": "...",
            "cc_id": "..."
          }
        ],
        "max_in_flight": ...
      },
      "documents_count": ...,
      "resolution": "..."
    },
    "http_status_code": 200
  }

```

|Key|Type|Description|
|---|----|-----------|
|`feed_call`|Boolean|If `true`, the Pipeline increments tha API meter. ???|
|`subpipeline_parameters`|object|If the Task was triggered by a parent Pipeline, the key-value pairs of parameters passed to this Task. ???|
|`llfeed_status`|object|??? -   `message_history`. \(array\) An array of strings containing the message history.
-   `messages`. \(array\) An array of strings containing messages.
-   `documents_count`. \(integer\) The number of documents processed.
-   `max_in_flight`. \(integer\) The maximum number of concurrent Task runs that the Org is allowed. ???
-   `summary`. \(string\) A summary of ???

|
|`class_fqid`|string|The fully-qualified ID of a Snap. It consists of the Snap class ID and the class version.|
|`snode_id`|string|The ID Of the Snaplex node that processed the Task run.|
|`ttl`|integer|A Task's ??? time to live, expressed in milliseconds ???.|
|`org_snode_id`|string|The ID of the Snaplex node that hosts the Org.|
|`cc_prepare_end_ms`|integer|???, expressed in milliseconds.|
|`parent_path`|string|The path to the parent Pipeline, if this Task is a child.|
|`delete_time`|string|When the Task was deleted. ??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`error_list`|array|???|
|`child_count`|integer|The number of children of this Task's Pipeline. ???|
|`data_locations`|array|An array of objects containing information about each data location \(source or target\). ???|
|`env_map`|object|???|
|`restart_attempts`|integer|The number of attempts to restart the Task after a failure or suspension.|
|`error_documents_count`|integer|The number of documents that had errors.|
|`env_map_list`|array|An array of Objects containing: -   `ciphertext`. \(string\) ???
-   `sym_key`. \(Object\) An object containing the `alias` and `key` of ???.

|
|`statistics_time_stamp`|string|??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`job_trigger`|string ???|???|
|`cc_fast_push_expire_time_ms`|integer|???, expressed in milliseconds.|
|`fault_injections`|string ???|???|
|`slserver_lease_expire_time`|string|??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`cc_poll_ms`|integer|???, expressed in milliseconds.|
|`instance_id`|string|The UUID of the Task run. ???|
|`mode`|string|The mode of the Task run. ??? Possible values:

-   `standard`
-   ???

|
|`async`|Boolean|If `true`, the Task was run asynchronously. Learn more: [Understanding Synchronous and Asynchronous Execution of Triggered Tasks](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/986285123/Understanding+Synchronous+and+Asynchronous+Execution+of+Triggered+Tasks?search_id=afeaec24-704d-45c9-af23-0c33f117fb44)

|
|`pipe_invoker`|string|How the Pipeline was invoked. Possible values:

-   `always_on`
-   `???`
-   `???`

|
|`create_time`|string|The time when the Task run was created. ??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`duration`|integer|The length of time the Task ran, expressed in milliseconds. ???|
|`notification`|object|Information about recipients of notifications.|
|`label`|string|The label or name of the Task run.|
|`state`|string|The status of the Task run. ??? Valid values:

-   started
-   ???

|
|`replicaset_label`|string|The label of ???|
|`invoker`|string|The user that invoked the Task run. ???|
|`cc_user`|string|The user that ???|
|`time_stamp`|string|The time when the Task run started. ??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`cc_external_uri`|string|The URI of the node where the Task is running. ???|
|`partition_snode_id`|string|The ID of the node partition where the Task is running. ???|
|`lint_id_list`|array|???|
|`reason`|string|The reason for running the Task, if specified. ???|
|`threads`|array|???|
|`prepare_handoff_timestamp`|string|The time when ??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`slot_count`|integer|???|
|`end_stage`|string|??? Possible values:

-   `EXECUTE`
-   ???

|
|`search`|string|The search string used to locate this Task run. ???|
|`limits`|string ???|???|
|`class_id`|string|The ID of the class that ???|
|`has_lints`|Boolean|If `true`, ???|
|`q_threshold_time`|string|The time when ??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`control_plane_scheduling`|array|An array of objects that contain ???|
|`suggest_uris`|string ???|???|
|`cc_end_ms`|integer|???, expressed in milliseconds.|
|`task_status`|array|???|
|`cc_prepare_start_ms`|integer|??? in milliseconds|
|`phase_snode_id`|string|???|
|`duration_ms`|integer|???, expressed in milliseconds.|
|`parent_ruuid`|string|Runtime ID of the \(parent\) Task that triggered this \(child\) Task.|
|`references`|array|An array of objects that contain ???|
|`do_start`|Boolean|If `true`, ???|
|`statistics`|object|???|
|`user_id`|string|???|
|`connect_pipeline_views`|Boolean|If `true`, ???|
|`container_type`|string|??? Possible values:

-   `regular`
-   ???

|
|`priority`|integer|The priority of this Task instance.|
|`instance_fqid`|string|The fully qualified ID of this Task instance.|
|`info_flag_list`|array|???|
|`runtime_path_id`|string|???|
|`lint_list`|array|???|
|`failure`|string ???|???|
|`state_log`|array|An array of objects containing changes in the state, the timestamp for each change, and other information. Possible values:

-   Started
-   Prepared
-   NoUpdate
-   ???

|
|`ruuid`|string|The Runtime ID of the Task run.|
|`parent_pipeline_fqid`|string|The fully qualified ID of the \(parent\) Pipeline that triggered this Task run.|
|`execution_timeout`|string ???|???|
|`path_id`|string|???|
|`plex_snode_id`|string|???|
|`error`|object|If errors occurred, an object containing metadata about the errors.|
|`plex_path`|string|The path to the Snaplex where the Task ran. ???|
|`invoker_snode_id`|string|The ID of the Snaplex node where the parent or invoker is located.|
|`invoker_path_id`|string|???|
|`snaplex_label`|string|The label or name of the Snaplex where the Task ran.|
|`platform_globals`|object|??? -   `task` contains the datetimes when the Task run started and ended.
-   ???

|
|`init_xid`|string|???|
|`nested_pipeline`|Boolean|If `true`, the Task run is for a nested Pipeline and was triggered by the Task running the parent Pipeline. ???|
|`project_snode_id`|string|The ID of the Snaplex node where the project is located.|
|`class_version`|string|The version of the class that ???|
|`warning_list`|array|If the Task run generated warnings, an array of objects containing metadata about the warnings.|
|`root_ruuid`|string|The ID of the root Task instance, if this Task is a descendant.|
|`cc_start_ms`|integer|The length of time since the Snaplex node was started, expressed in milliseconds.|
|`poll_time_stamp`|string|??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`artifacts_map`|object|???|
|`artifact_snap_id_map`|object|???|
|`ccid`|string|The ID of the Snaplex node where the Task ran.|
|`delivery_options`|object|???|
|`metrics`|object|Information about ???. -   `queuedCount` – The number of ??? waiting in the queue.
-   `totalSnapDelay` – The total number of milliseconds that Snaps within the Task run were delayed. ???
-   `idleTime` – expressed in milliseconds.
-   `memoryOverhead` – ???
-   `inFlightCount` – The number of ???
-   `startTime` – The number of milliseconds since ??? started.

|
|`expire_time`|string|When the Task run expires. ??? Format: [UTC](https://www.w3.org/TR/NOTE-datetime)

|
|`runtime_label`|string|???|
|`close_reason`|string|Reason for closing the Task.|
|`cc_stop_ms`|integer|???, expressed in milliseconds.|
|`root_path`|string|???|
|`invoker_name`|string|???|
|`error_fp_list`|array|???|
|`flags`|object|???|
|`captured_env_map`|object|???|
|`llfeed_context`|object|???|
|`documents_count`|integer|???|
|`resolution`|string ???|???|

**Parent topic:**[SnapLogic Public APIs](../public-apis/public-apis.md)

**Related information**  


[GET /runtime/\{org\}](../public-apis/get-runtime-org.md)

[GET /runtime/api-stats/\{org\}](../public-apis/get-runtime-apistats-org.md)

[GET /runtime/api-stats/\{org\}/daily](../public-apis/get-runtime-apistats-org-daily.md)

[GET /runtime/api-stats/\{org\}/concurrent](../public-apis/get-runtime-apistats-org-concurrent.md)

[POST /runtime/start/\{org\}/\{ruuid\}](../public-apis/post-runtime-start-org-ruuid.md)

[POST /runtime/stop/\{org\}/\{ruuid\}](../public-apis/post-runtime-stop-org-ruuid.md)

