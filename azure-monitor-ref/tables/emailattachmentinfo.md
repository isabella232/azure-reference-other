---
title: Azure Monitor Logs reference - EmailAttachmentInfo
description: Reference for EmailAttachmentInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/29/2022
---

# EmailAttachmentInfo

 Office 365 attached emails information.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DetectionMethods | string | Sender email address in the from header, which is visible to email recipients on their email clients |
| FileName | string | Name of the file that the recorded action was applied to |
| FileType | string | File extension type |
| NetworkMessageId | string | Unique identifier for the email, generated by Office 365 |
| RecipientEmailAddress | string | Email address of the recipient, or email address of the recipient after distribution list expansion |
| RecipientObjectId | string | Email recipient unique identifier in Azure AD |
| ReportId | string | Unique identifier for the event |
| SenderDisplayName | string | Sender email address in the from header, which is visible to email recipients on their email clients |
| SenderFromAddress | string | Sender domain in the from header, which is visible to email recipients on their email clients |
| SenderObjectId | string | Sender email address in the from header, which is visible to email recipients on their email clients |
| SHA256 | string | SHA-256 of the file that the recorded action was applied to |
| SourceSystem | string |  |
| TenantId | string |  |
| ThreatNames | string | Sender email address in the from header, which is visible to email recipients on their email clients |
| ThreatTypes | string | Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats |
| TimeGenerated | datetime | Date and time (UTC) when the record was generated |
| Type | string | The name of the table |
