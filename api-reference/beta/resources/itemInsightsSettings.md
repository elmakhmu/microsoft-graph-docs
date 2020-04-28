---
title: "itemInsightsSettings resource type"
description: "Represents a company's itemInsight settings."
localization_priority: Normal
author: "elmakhmu"
ms.prod: ""
doc_type: resourcePageType
---

# itemInsightsSettings resource type

Namespace: microsoft.graph

Represents a company's itemInsights settings.

## Properties
| Property   | Type|Description|
|:---------------|:--------|:----------|
|isEnabledInOrganization|Boolean| **true**(default) if organization itemInsights are enabled; **false** if organization itemInsights are disabled for all users without exceptions. Not required.|
|disabledForGroup|String|an Id of security AAD group, whose members' itemInsights are disabled. Not required.|

## JSON representation

Here is a JSON representation of the resource


```json
{
  "isEnabledInOrganization": "boolean",
  "disabledForGroup": "string"
}
```
