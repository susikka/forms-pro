---
title: "Work with environments in Microsoft Forms Pro | MicrosoftDocs"
description: "Learn about working with environments in Microsoft Forms Pro"
keywords: ""
author: sbmjais
ms.author: shjais
manager: shujoshi
applies_to: 
ms.date: 06/17/2020
ms.service: forms-pro
ms.topic: article
ms.assetid: 90EFF51F-36E3-4973-8768-82F12629B0B3
ms.custom: 
search.appverid:
  - FPR160
---

# Work with environments

An environment is a space to store, manage, and share your organization's business data, apps, and flows. It also serves as a container to separate apps that might have different roles, security requirements, or target audiences. More information: [Environments overview](https://docs.microsoft.com/power-platform/admin/environments-overview)

You can create environments for different purposes such as survey development, testing, and production. After developing and testing the survey, you can copy the survey to the production environment.

When you sign in to Microsoft Forms Pro, only the surveys that are available in the selected environment are displayed. When you create a survey, the survey is connected to the selected environment and isn't available in other environments. The invitations and responses are stored in the same environment in which the survey was created.

You can switch the environment at any time and start working in it. You can also copy a survey from one environment to another. When you copy a survey to another environment, only the survey structure and its branching rules are copied&mdash;invitations, responses, and associated flows aren't copied.

To work with surveys in an environment, install the [Forms Pro app from Microsoft AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.shimla?tab=Overview), and assign the Survey Owner role to users. If you switch to an environment that doesn't have Forms Pro, an error message is displayed.

When you install the Forms Pro app, an application user named Microsoft Forms Pro is created automatically. This user is created to allow Forms Pro Azure service to authenticate with Common Data Service using Server-to-Server (S2S) authentication, and is primarily used for pushing survey data. The user is a non-interactive and non-login user. It is assigned Survey Services Administrator and System Administrator roles. More information on S2S authentication: [Build web applications using Server-to-Server (S2S) authentication](https://docs.microsoft.com/powerapps/developer/common-data-service/build-web-applications-server-server-s2s-authentication)

> [!NOTE]
> - If you have organizations for Dynamics 365 Sales, Customer Service, Marketing, and Talent, Forms Pro entities are already installed in these organizations.
> - A default environment is based on Common Data Service. Before planning a large scale deployment, see [service protection API limits](https://docs.microsoft.com/powerapps/developer/common-data-service/api-limits). To learn more about the default environment, see [default environment](https://docs.microsoft.com/power-platform/admin/environments-overview#the-default-environment).

## Privileges required

- Ensure that you've assigned the Survey Owner role to users.
- If you've created any custom entities that you want Forms Pro to interact with, assign the **Append To** privilege of the entities to the user.

### Minimum privileges for a custom role

If you've created a custom security role and want to use it as a survey owner, ensure that the custom role has User permission on the entities used by Forms Pro. The following table shows the required and optional privileges for the entities.

A required privilege is denoted by ![Required](media/required-icon.png "Required").

An optional privilege is denoted by ![Optional](media/optional-icon.png "Optional").

If you provide the optional privileges, additional actions can be performed by the user who is assigned the custom role. For example, the Read privilege is required for the Contact entity and is used to associate invitations with a specific contact. Other privileges, such as Create and Write, are optional. If you provide Create and Write privileges, a user can perform these operations on a contact. If you provide only the Read privilege, and you want a particular user to perform create and write operations also on a contact, you can provide Create and Write privileges to the user through other security roles.

|Entity                            |Create   |Read     |Write    |Delete   |Append   |Append To|Assign |Share   |
|----------------------------------|---------|---------|---------|---------|---------|--------|--------|--------|
|Forms Pro survey                  |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
|Forms Pro survey email template   |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
|Forms Pro Survey question         |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
|Forms Pro Survey question response|![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
|Forms Pro unsubscribed recipient  |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional") |![Optional](media/optional-icon.png "Optional") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
|Activity                          |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
|Contact                           |![Optional](media/optional-icon.png "Optional") |![Required](media/required-icon.png "Required") |![Optional](media/optional-icon.png "Optional") |![Optional](media/optional-icon.png "Optional") |![Optional](media/optional-icon.png "Optional") |![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|![Optional](media/optional-icon.png "Optional")|
||||||||||

### See also

[Change an environment](change-environment.md)<br>
[Copy a survey to another environment](copy-survey-environment.md)
