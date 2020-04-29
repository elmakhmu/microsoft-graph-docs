---
title: "Get organization settings"
description: "Read the organization settings object."
author: "elmakhmu"
localization_priority: Normal
ms.prod: ""
doc_type: apiPageType
---

# Get settings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read organization [organizationsettings](../resources/organizationsettings.md) object.
To learn how to update the properties of the [organizationsettings](../resources/organizationsettings.md) object, see [organizationsettings-update](organizationsettings-update.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Organization.ReadWrite.All |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Organization.ReadWrite.All |

## HTTP request

```http
GET /organization/settings/
```
## Request headers

| Name       | Description|
|:-----------|:----------|
| Authorization  | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and [organizationsettings](../resources/organizationsettings.md) object in the response body.

> [!NOTE]
> This endpoint does not check existence of an AAD Group. Hence, if the AAD group has been deleted, then this method will show previously predefined value of 'disabledForGroup' property but item insights of these group members might be enabled. 

## Example

##### Request

```http
GET https://graph.microsoft.com/beta/organization/settings
```

##### Response

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "itemInsights": 
  {
    "isEnabledInOrganization": true,
    "disabledForGroup": "edbfe4fb-ec70-4300-928f-dbb2ae86c981"
  }
}
```
