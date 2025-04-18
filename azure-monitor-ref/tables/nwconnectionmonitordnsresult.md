---
title: Azure Monitor Logs reference - NWConnectionMonitorDNSResult
description: Reference for NWConnectionMonitorDNSResult table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/29/2022
---

# NWConnectionMonitorDNSResult

 Connection Monitor DNS result records.

## Categories

- Network
## Solutions

- LogManagement
## Resource types

- Network Watcher - Connection Monitor




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ChecksFailed | int | The total number of checks failed under the test |
| ChecksTotal | int | The total number of checks done under the test |
| ConnectionMonitorResourceId | string | The connection monitor resource id of the test |
| DestinationAddress | string | The address of the destination configured for the test |
| DestinationAgentId | string | The destination agent id |
| DestinationIP | string | The IP address of the destination |
| DestinationName | string | The destination end point name |
| DestinationPort | int | The destination port configured for the test |
| DestinationResourceId | string | The resource id of the Destination machine |
| DestinationSubnet | string | If applicable, the subnet of the destination |
| DestinationType | string | The type of the destination machine configured for the test |
| DomainName | string | The domain name of DNS Test |
| Protocol | string | The protocol of the test |
| RecordId | string | The record id for unique identification of test result record |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseRecordCount | int | The total count of DNS response records |
| ResponseRecords | string | The DNS Response records |
| ResponseRecordType | string | The type of DNS response record |
| SourceAddress | string | The address of the source configured for the test |
| SourceAgentId | string | The source agent id |
| SourceIP | string | The IP address of the source |
| SourceName | string | The source end point name |
| SourceResourceId | string | The resource id of the source machine |
| SourceSubnet | string | The subnet of the source |
| SourceSystem | string |  |
| SourceType | string | The type of the source machine configured for the test |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TestConfigurationName | string | The test configuration name to which the test belongs to |
| TestGroupName | string | The test group name to which the test belongs to |
| TestResult | string | The result of the test |
| TestResultCriterion | string | The result criterion of the test |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| ValidationChecks | string | The validation checks of DNS Result |
| ValidationIssues | string | The issues identified as part of DNS Test |
