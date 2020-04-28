---
title: "organizationSettings resource type"
description: "The current organization settings. "
author: "elmakhmu"
localization_priority: Normal
ms.prod: "microsoft-identity-platform"
doc_type: resourcePageType
---

# organizationSettings resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The current organization settings. 
To learn how to get or update organization settings, see [Get settings](../api/organizationsettings-get.md) and [Update settings](../api/organizationsettings-update.md).

This resource supports:

- Checking organization-wide parameters, namely accessibility item insights for a group of users or for an entire organization.
- Configuring organization-wide parameters, namely disabling or enabling item insights for a group of users or for an entire organization.


## Methods
| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get organization settings](../api/organizationsettings-get.md) |[organizationSettings](../resources/organizationsettings.md)| Get the organization settings. |
|[Update organization settings](../api/organizationsettings-update.md) |[organizationSettings](../resources/organizationsettings.md)| Update the organization settings. |

## Properties

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|itemInsights|[itemInsightsSettings](itemInsightsSettings.md)| Properties that you can use to tune item insights availability|

## Relationships

?

## JSON representation

Here is a JSON representation of the resource.

```json
{
  "itemInsights": 
  {
    ...
  }
}

```
