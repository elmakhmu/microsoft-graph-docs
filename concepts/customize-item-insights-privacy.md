---
title: "Overview of customizing item insights privacy in Microsoft Graph"
description: ""
author: "elmakhmu"
localization_priority: Priority
ms.prod: "insights"
ms.custom: scenarios:getting-started
---
IN PROGRESS
OfficeGraph -> ItemInsights
Angela. Because we don’t want the term “Office Graph” and related API “officeGraphInsights” to remain in the lingo, aside from the docs, we will still need to message out, in a blog post and other means (like contacting existing customers?): 
•	By a certain date, customers should update their code to access the 3 nav properties through itemInsights. 
•	Technically, the timeline is not enforceable because the officeGraphInsights will continue to be available.


# Overview of customizing item insights privacy in Microsoft Graph

## item insights limitation settings
Trending and some types of used insights can be disabled for members of a specific security AAD group or for entire organization by updating [organizationsettings](organizationsettings.md) object using [organizationsettings-update](../api/organizationsettings-update.md). 

Following privacy configurations are available for administrators to set up:<br>
1. Item insights are enabled for all users in the organization without exceptions<br>
     'isEnabledInOrganization' == true<br>
     'disabledForGroup' == empty<br>
2. Item insights are enabled in the organization, but item insights of AAD group need to be disabled<br>
     'isEnabledInOrganization' == true<br>
     'disabledForGroup' == ID of an security AAD group, where administrtator collect all users, which item insights need to be disabled.<br>
3. Item insights are disabled for all users in the organization without exceptions. <br>
     'isEnabledInOrganization' == false<br>
     'disabledForGroup' parameter value does not matter

UX and API dependencies: 
1.	If a user’ item insights have been disabled, then the user himself cannot access to:<br>
1.1.	The "Suggested sites" list on the SharePoint start page.<br>
1.2.	The "Discover" list in OneDrive, in the Outlook mobile app, and on the Microsoft Office Home page.<br>
1.3.	Documents on his Delve page <br>
1.4.	Trending around him document though [insights-list-trending](../api/insights-list-trending.md)<br>
2.	If a user’ item insights have been disabled, then other users cannot access following:<br>
2.1.	Last modified by this user documents on his profile card, Delve page and through [insights-list-used](../api/insights-list-used.md)<br>
2.2.	Trending around this user documents in his Delve page and through [insights-list-trending](../api/insights-list-trending.md)
