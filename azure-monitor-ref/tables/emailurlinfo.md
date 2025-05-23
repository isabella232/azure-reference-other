---
title: Azure Monitor Logs reference - EmailUrlInfo
description: Reference for EmailUrlInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/29/2022
---

# EmailUrlInfo

 Office 365 emails URLs information.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| NetworkMessageId | string | Email unique identifier generated by Office 365 |
| ReportId | string | Unique identifier for the event |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time (UTC) when the record was generated |
| Type | string | The name of the table |
| Url | string | Information about URLs on Office 365 emails |
| UrlDomain | string | Domain part of the Url |
