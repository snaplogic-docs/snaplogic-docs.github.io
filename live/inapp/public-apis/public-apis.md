# SnapLogic Public APIs {#public-apis .concept}

## Overview { .section}

SnapLogic Public APIs provide basic functionality that you can use to programmatically manage your integration. Note that you can also create your own custom APIs from your Pipelines using the API Management tool.

-   The timeout for these APIs is set to 15 minutes. This timeout setting can be changed on the client-side network, but it remains 15 minutes in the SnapLogic Platform.
-   The total API limit is affected only by triggered Pipeline executions; it is not affected by the use of SnapLogic Public APIs.

## Authentication { .section}

API requests are authenticated using basic authentication over HTTPS. Additional authentication methods are under consideration for future updates.

You can run these APIs regardless of the privileges or user roles assigned to you in your Org. Access to the information returned by these APIs is based on asset permissions, which are set in [SnapLogic Manager](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1439061).

If your account is locked or your password is expired, you cannot invoke SnapLogic Public APIs.

-   **[Permissions in Manager and in APIs](../public-apis/api-perms-vs-manager-perms.md)**  
Mapping between Manager permissions and API permissions.
-   **[Reference: Activity Metadata](../public-apis/ref-activity-metadata.md)**  
Information about an activity.

