---
title: Azure Monitor Logs reference - ADFSSignInLogs
description: Reference for ADFSSignInLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/29/2022
---

# ADFSSignInLogs

 Logs generated by Active Directory Federation Service.

## Categories

- Audit
- Security
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AlternateSignInName | string | Provides the on-premises UPN of the user sign-ing into Azure AD.e.g. Phone number sign-in |
| AppDisplayName | string | The string name of the OAuth client in the request displayed in the Azure Portal |
| AppId | string | A unique ID of the Oauth Client ID in the request |
| AuthenticationDetails | string | A record of each step of authentication undertaken in the sign-in |
| AuthenticationProcessingDetails | string | Provides the details associated with authentication processor |
| AuthenticationRequirement | string | Type of authentication required for the sign-in.  If set to multiFactorAuthentication, an MFA step was required.  If set to singleFactorAuthentication, no MFA was required |
| AuthenticationRequirementPolicies | string | Set of CA policies that apply to this sign-in, each as CA: policy name, and/or MFA: Per-user |
| Category | string | Category of the sign-in event |
| ConditionalAccessPoliciesV2 | dynamic | Details of the conditional access policies being applied for the sign-in |
| ConditionalAccessStatus | string | Status of all the conditionalAccess policies related to the sign-in |
| CorrelationId | string | ID to provide sign-in trail |
| CreatedDateTime | datetime | Datetime of the sign-in activity |
| DeviceDetail | string | Details of the device used for the sign-in |
| DurationMs | long | The duration of the operation in milliseconds |
| Id | string | Unique ID representing the sign-in activity |
| Identity | string | The identity from the token that was presented when you made the request. It can be a user account, system account, or service principal |
| IPAddress | string | IP address of the client used to sign in |
| IsInteractive | bool | Indicates if a sign-in is interactive or not |
| Level | string | The severity level of the event |
| Location | string | The region of the resource emitting the event |
| NetworkLocationDetails | string | Provides the details associated with authentication processor |
| OperationName | string | For sign-ins, this value is always Sign-in activity |
| OperationVersion | string | The REST API version that's requested by the client |
| OriginalRequestId | string | The request id of the first request in the authentication sequence |
| ProcessingTimeInMs | string | Request processing time in milliseconds in AD STS |
| Requirement | string | If the authentication is a primary or secondary authentication. Can be not set. |
| ResourceDisplayName | string | The string name of the application the user signed into displayed in the Azure Portal |
| ResourceGroup | string | Resource group for the logs |
| ResourceIdentity | string | A unique ID application ID the user signed into of the request |
| ResourceTenantId | string | The resource tenant ID for cross-tenant scenarios |
| ResultDescription | string | Provides the error description for the sign-in operation |
| ResultSignature | string | Contains the error code, if any, for the sign-in operation |
| ResultType | string | The result of the sign-in operation can be Success or Failure |
| SourceSystem | string | Details of source system of the object being provisioned |
| Status | string | Details of the sign-in status |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time of the event in UTC |
| TokenIssuerName | string | Name of the identity provider (e.g. sts.microsoft.com ) |
| TokenIssuerType | string | Type of identityProvider (Azure AD, AD Federation Services) |
| Type | string | The name of the table |
| UniqueTokenIdentifier | string | Unique token identifier for the request |
| UserAgent | string | User Agent for the sign-in |
| UserDisplayName | string | Display name of the user that initiated the sign-in |
| UserId | string | ID of the user that initiated the sign-in |
| UserPrincipalName | string | User principal name of the user that initiated the sign-in |
