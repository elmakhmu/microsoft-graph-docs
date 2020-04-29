---
title: "Update organization settings"
description: "Update the properties of the organizationsettings object."
author: "elmakhmu"
localization_priority: Normal
ms.prod: ""
doc_type: apiPageType
---

# Update settings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update organization [organizationsettings](../resources/organizationsettings.md) object.
To learn how to get the properties of the [organizationsettings](../resources/organizationsettings.md) object, see [organizationsettings-get](organizationsettings-get.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Organization.ReadWrite.All |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Organization.ReadWrite.All |

## HTTP request

```http
PATCH /organization/settings
```

## Request headers

| Header       | Value|
|:-----------|:------|
| Authorization  | Bearer {token}. Required.  |
| Content-Type  | application/json  |

## Request body

In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|isEnabledInOrganization|Boolean|(default true) When set to 'true', all users' item insights are enabled, except for members of one security AAD group, if it specified by the 'disabledForGroup' property. When set to 'false', all users' item insights are disabled without any exceptions.|
|disabledForGroup|String|(default empty) an ID of security AAD group, whose members' item insight are disabled|

> [!NOTE]
> This endpoint verifies validity of a property value but does not check existence of an AAD Group. 

## Example 

##### Request

Here is an example request on how admin updates 'disabledForGroup' privacy setting in order to prohibit displaying users' item insights of an particular AAD group.

```http
PATCH https://graph.microsoft.com/beta/organization/settings
Content-type: application/json
Content-length: 37

{
  "disabledForGroup": "edbfe4fb-ec70-4300-928f-dbb2ae86c981"
}
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

