---
title: "officeGraphInsights resource type"
description: "Represents the base type for [itemInsights](itemInsights.md). officeGraphInsights is for backward compatibility from earlier versions of the insights API. Use only itemInsights when accessing the insights API."
author: "simonhult"
localization_priority: Priority
ms.prod: "insights"
doc_type: resourcePageType
---

# officeGraphInsights resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Insights are relationships calculated using advanced analytics and machine learning techniques. You can, for example, identify OneDrive documents trending around users.

Insights are returned by the following APIs:

- [Trending](insights-trending.md) - returns documents from OneDrive and from SharePoint sites trending around a user.
- [Used](insights-used.md) - returns documents viewed and modified by a user. Includes documents the user used in OneDrive for Business, SharePoint, opened as email attachments, and as link attachments from sources like Box, DropBox and Google Drive.
- [Shared](insights-shared.md) - returns documents shared with a user. Documents can be shared as email attachments or as OneDrive for Business links sent in emails.

Each insight is returned with a `resourceVisualization` and `resourceReference` complex value type (CVT). The resourceVisualization CVT contains properties such as `title` and `previewImageUrl`. Microsoft uses the visualization properties to render the files in experiences like Office Delve.

## Relationships

| Relationship      | Type          | Description  |
| ------------- |---------------| -------------|
| trending    	| [trending](insights-trending.md) collection		| Access this property from the derived type [itemInsights](itemInsights.md) |
| used    	| [usedInsight](insights-used.md) collection		| Access this property from the derived type [itemInsights](itemInsights.md)|
| shared    	| [sharedInsight](insights-shared.md) collection		| Access this property from the derived type [itemInsights](itemInsights.md) |

## JSON representation

Here is a JSON representation of the resource

```json
{
  "id": "string",
  "iteminsights": [ { "@odata.type": "microsoft.graph.trending" } ],
  "used": [ { "@odata.type": "microsoft.graph.used" } ],
  "shared": [ { "@odata.type": "microsoft.graph.shared" } ]
}
```
