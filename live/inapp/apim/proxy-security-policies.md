# Proxy Security Policies {#proxy-security-policies .concept}

Manage and apply security policies for proxies and endpoints.

## Overview { .section}

[Supported security policies](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1068859547/API+Policy+Manager#APIPolicyManager-SupportedAPIPolicies) for proxies and endpoints are the same as those for APIs and API Versions.

To apply security policies to the proxy or to the endpoints, editing the proxy settings or the endpoint settings.

**Note:** A proxy and its endpoints can have a maximum of one enabled policy of each policy type. If both the proxy and the endpoint have defined policies of the same type, the endpoint policy has precedence over the proxy policy.

Learn more about each policy type and its settings: [Supported API Policies](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1068859547/API+Policy+Manager#APIPolicyManager-SupportedAPIPolicies)

## Viewing Security Policies { .section}

To view the list of security policies that are defined for a proxy or for an endpoint, go to the details page of the proxy or the endpoint.

-   To go to the proxy details page,
    1.  In the API Manager, go to the **APIs & Proxies** tab.
        1.  In SnapLogic **Manager**, go to **API Management** \> **API Manager**.
        2.  In the API Manager, go to the **APIs & Proxies** tab.
        3.  Set **Filter by Type** to **Proxy** and click **Search**.
    2.  Click the proxy's name in the list.
-   To go to the endpoint details page,
    1.  In the API Manager, open a proxy for editing, then go to the **Proxy Endpoints** tab.
        1.  In SnapLogic **Manager**, go to **API Management** \> **API Manager**.
        2.  In the API Manager, go to the **APIs & Proxies** tab.
        3.  Set **Filter by Type** to **Proxy** and click **Search**.
        4.  Click the proxy's name in the list.
        5.  Go to the **Proxy Endpoints** tab.
    2.  Click the endpoint's name in the list.

The defined security policies are listed in the table at the bottom.

|Field|Description|
|-----|-----------|
|**Policy**|The name of the policy instance.|
|**Type**|The type of the security policy.|
|**Owner**|The owner of the policy instance, typically the creator of the policy instance.|
|**Updated**|The datetime when the policy was last updated.|
|**Status**|Indicates whether the policy is **Enabled** or **Disabled**.|

## Adding a Policy { .section}

To add and apply security policies to your proxy or endpoint, click the plus icon \(![plus symbol](../common/../img/icons/add.svg)\) and choose a policy type.

The fields in the Add Policy dialog vary according to the policy type.

## Editing a Policy { .section}

To edit a policy, click its name on the list.

The fields in the Edit Policy dialog vary according to the policy type.

## Viewing the Hierarchy of Policies { .section}

To view the hierarchy of the applied policies, click **View Applied Policies** and go to the **Hierarchy** tab.

![Hierarchy tab in the Related Policies dialog of an endpoint](../img/apim-proxy-endpoint-policies-hierarchy.png)

**Parent topic:**[Proxies for APIs](../apim/proxies.md)

**Related information**  


[API Policy Manager](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1068859547/API+Policy+Manager)

[Supported API Policies](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1068859547/API+Policy+Manager#APIPolicyManager-SupportedAPIPolicies)

