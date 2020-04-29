---
title: "itemInsightsSettings resource type"
description: "Complex type containing itemInsights settings."
localization_priority: Normal
author: "elmakhmu"
ms.prod: ""
doc_type: resourcePageType
---

# itemInsightsSettings resource type

Namespace: microsoft.graph

Complex type containing itemInsights settings.

## Properties
| Property   | Type|Description|
|:---------------|:--------|:----------|
|isEnabledInOrganization|Boolean| **true**(default) if organization itemInsights are enabled; **false** if organization itemInsights are disabled for all users without exceptions. Not required.|
|disabledForGroup|String|(default empty) an Id of security AAD group, whose members' itemInsights are disabled. Not required.|

## JSON representation

Here is a JSON representation of the resource


```json
{
  "isEnabledInOrganization": "boolean",
  "disabledForGroup": "string"
}
```
