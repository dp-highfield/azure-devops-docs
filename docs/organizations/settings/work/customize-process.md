---
title: Customize a project  
titleSuffix: Azure DevOps Services
description: Your guide to configuring and customizing work tracking processes for a project by customizing an inherited process
ms.custom: inherited-process
ms.technology: devops-agile
ms.assetid: 31CA1DCB-8E3E-4B9E-A64A-D47DF23490A3   
ms.author: kaelli
author: KathrynEE
monikerRange: '>= azure-devops-2019'
ms.topic: tutorial
ms.date: 04/22/2019
---

# Customize a project using an inherited process

[!INCLUDE [version-gt-eq-2019](../../../includes/version-gt-eq-2019.md)]


::: moniker range=">= azure-devops-2020"

Each project is based on a process that defines the building blocks for tracking work. The first project you create uses one of the default processes&mdash;[Agile](../../../boards/work-items/guidance/agile-process.md), [Basic](../../../boards/get-started/plan-track-work.md), [Scrum](../../../boards/work-items/guidance/scrum-process.md), or [CMMI](../../../boards/work-items/guidance/cmmi-process.md). 

::: moniker-end

::: moniker range="azure-devops-2019"

Each project is based on a process that defines the building blocks for tracking work. The first project you create uses one of the default processes&mdash;[Agile](../../../boards/work-items/guidance/agile-process.md), [Scrum](../../../boards/work-items/guidance/scrum-process.md), or [CMMI](../../../boards/work-items/guidance/cmmi-process.md). 

::: moniker-end

You can only customize inherited processes. Any changes you make to the inherited process automatically appears in the projects that use that process. 

[!INCLUDE [temp](../includes/note-on-prem-link.md)]



The general sequence for customizing a project is to customize an inherited process, verify your customizations, and then change the process of the project(s) to use that process. 

[![Create an inherited process](media/process/customize-work-phase2-step1.png)](manage-process.md)[![Customize the inherited process](media/process/customize-work-phase2-step2.png)](customize-process.md)[![Apply inherited process to  project(s)](media/process/customize-work-phase2-step3.png)](manage-process.md#migrate)![Refresh and verify changes](media/process/customize-work-phase2-step4.png)  


You primarily customize a process by adding or modifying a work item type (WIT) defined for that process.  

Learn how to perform these tasks:  

> [!div class="checklist"] 
> * Open **Settings>Process**
> * Create an  inherited process to customize   
> * Add or modify a field 
> * Add or modify a rule for a work item type 
> * Add or modify work item types 
> * Modify the workflow of a work item type 
> * Add or modify a custom control   
> * Add an extension to a work item type
> * Verify the customizations you made  
> * Change the process used by a project 
 
[!INCLUDE [temp](../includes/note-audit-log-support-process.md)]

[!INCLUDE [temp](../includes/process-prerequisites.md)] 

[!INCLUDE [temp](../includes/open-process-admin-context-ts.md)]

[!INCLUDE [temp](../includes/automatic-update-project.md)] 
 
[!INCLUDE [temp](../includes/create-inherited-process.md)] 


## Add or modify a field 

Locked :::image type="icon" source="media/process/locked-icon.png" border="false"::: fields and inherited :::image type="icon" source="media/process/inherited-icon.png" border="false"::: fields correspond to fields inherited from a system process. You can't customize locked fields. You can customize some options for inherited fields. You can fully customize fields that you add to a process. 

1. To begin, choose your inherited process, and then choose the WIT you want to customize. 

2. To add a field, choose the :::image type="icon" source="media/process/new-field-icon.png" border="false"::: (**New Field** icon).  

	> [!div class="mx-imgBorder"]  
	> ![Process Work Item Types page, Add a field to a WIT](media/field/bug-new-field.png)

	In the dialog that opens, choose the type of field that you want to add. To learn more, see the following articles:   
	- [Integer](customize-process-field.md#add-field)  
	- [Picklist (drop-down menu)](customize-process-field.md#pick-list)  
	- [Person-name/Identity](customize-process-field.md#identity)  
	- [Rich-text or HTML](customize-process-field.md#html)  
	- [Checkbox (Boolean)](customize-process-field.md#boolean-field)

1. To modify an existing field, you can exercise these choices: 

	- [Change the field label](customize-process-field.md#rename-field)  
	- [Show/Hide field on form](customize-process-field.md#show-hide-field)  
	- [Set Required/Default options](customize-process-field.md#options)  
	- [Move the field within the layout](customize-process-form.md#move-field)
	- [Remove field from the form](customize-process-field.md#remove-field) 

## Add or modify a rule for a work item type
 
You add rules to support specific workflow and business use cases. Rules allow you to clear the value of a field, copy a value into a field, and apply values based on dependencies between different fields' values. 

To add a rule, choose your inherited process, the work item type, and then choose **Rules**, and then choose **New rule**.   

> [!div class="mx-imgBorder"]  
> ![Process, WIT, Bug, Layout, New custom control](media/rules/custom-rule-create-rule.png) 

To learn more, see [Rules and rule evaluation](custom-rules.md).

## Add or modify work item types

You use different WITs to plan and track different types of work. The main reason you add a custom WIT is to customize the web form and workflow states to meet specific business use cases.

1. To begin, choose your inherited process, and then choose the WIT you want to customize. 

1. From the **Work Item Types** page, choose the :::image type="icon" source="../../../media/icons/blue-add-icon.png" border="false"::: **New work item type**.

	<img src="media/process/cpwit-add-new-wit.png" alt="Process, Inherited process, Work Item Types, Add new work item type" />

2. Name the WIT and optionally specify a description, icon and color. The icon and color you specify appear throughout the web portal, including on the work item form and when associated work items appear on a backlog, boards, query results, and more. 

	<img src="media/process/cwit-create-wit-ticket.png" alt="Create new work item type dialog" /> 

	Click **Create** to save. 

3. You can now add fields to the WIT, or customize it in the following ways:  
	- [Modify the workflow](#workflow)  
	- [Add or remove a custom control](#custom-control)  
	- [Add an extension](#extension) 
	- [Add/move/remove custom groups](customize-process-form.md#groups)  
	- [Add/move/delete custom pages](customize-process-form.md#pages)  


<a id="workflow" />

## Modify the workflow of a work item type 

Workflow states allow you to track the status of a work item as it moves from new to completed. 

1. To modify a workflow, choose your inherited process, the WIT, and then the **States** page.  

	> [!div class="mx-imgBorder"]  
	> ![Process page, Bug WIT, States tab, Add state](media/process/cpworkflow-add-state.png) 

1. You can modify the workflow in the following ways:   
	- [Hide a workflow state](customize-process-workflow.md#hide-state) 
	- [Add a state](customize-process-workflow.md#add-states)  
	- [Edit a state (change color or category)](customize-process-workflow.md#edit-state)  
	- [Remove a state](customize-process-workflow.md#remove-state)     
 
<a id="custom-control" />

## Add a custom control    

Custom controls provide additional functionality to a work item form. 

- To add a custom control, choose your inherited process, the WIT, and then **Add custom control**.

	> [!div class="mx-imgBorder"]  
	> ![Choose your inherited process, the WIT, and then Add custom control.](media/process/cpcontrols-add-custom-control.png) 

To learn more, see [Add extensions and custom controls to a work item type](custom-controls-process.md).


<a id="extension" /> 

## Add an extension to a work item type

An extension is an installable unit that contributes new capabilities to your project.
  
> [!NOTE]   
> Group and Page extensions are automatically added to all WITs for all processes, both system and  inherited . You can choose to hide an extension for selected WITs within an  inherited process. 

1. To add an extension to a work item type, choose your inherited process, the WIT, and then choose **Get extensions**.
 
	> [!div class="mx-imgBorder"]  
	> ![Process, WIT, Bug, Layout, Get extensions](media/process/cprocess-choose-extensions.png) 

1. Select the extension you want to add. Here we choose the Work item checklist.

2. Select the organization you want to add it to and choose **Install**.  

	> [!div class="mx-imgBorder"]  
	> ![Visual Studio Marketplace, install extension](media/process/cprocess-install-extension.png) 

	Extensions are available to add to all projects and processes. 

3. Return to the process and WIT and verify the location of the extension is where you want it. Look for it at the bottom of the middle column and drag it to where you want it on the form. 

	> [!div class="mx-imgBorder"]  
	> ![Group extension on Bug work item form](media/process/cpfield-add-checklist-extension.png) 

## Modify the backlog and boards 

You can add additional WITs to a backlog level or add another portfolio backlog. As shown below, we've added a third level portfolio backlog labeled *Initiatives* which tracks the custom *Initiative* WIT, and we've renamed the product backlog to *Stories and Tickets* to indicate that we not only track *User Stories*, but also *Customer Tickets* on the product backlog. 
 
> [!div class="mx-imgBorder"]  
> ![Changes made to the backlog levels](media/process/process-backlog-boards-intro.png) 

1. To modify the backlogs  and boards configuration, begin by choosing your inherited process, and then choose the **Backlog levels** page. 

	> [!div class="mx-imgBorder"]  
	> ![Web portal, Admin context, Process page, open Backlog levels](media/process/process-backlog-levels-open.png) 

1. You can modify the backlog and board configuration in the following ways:    
	- [Add a custom WIT to a backlog or board](customize-process-backlogs-boards.md)  
	- [Change the default WIT](customize-process-backlogs-boards.md)  
	- [Rename the requirement backlog](customize-process-backlogs-boards.md#edit-product-backlog)  
	- [Rename a portfolio backlog](customize-process-backlogs-boards.md#edit-portfolio-backlog)  
	- [Add a portfolio backlog which displays custom WITs](customize-process-backlogs-boards.md#portfolio-backlogs)  
	- [Edit or rename a portfolio backlog](customize-process-backlogs-boards.md#edit-portfolio-backlog)  
	- [Delete the top-level custom portfolio backlog](customize-process-backlogs-boards.md#edit-portfolio-backlog) 


<a id="verify">  </a>

## Verify the customization you made 

We recommend that you create a test project and apply your customized inherited process to it to verify the changes you've made. All customizations made to a process go into effect immediately on all projects. If you want to stage your changes, you can do that using one of two methods: 
- [Create a test project and copy of your customized process](#test-project-copy-process)
- [Create a test organization and import/export your process](#test-import-export-process)

<a id="test-project-copy-process" />

### Create a test project and copy of your customized process

1. Open the **All processes** page, and choose the &hellip; context menu for the process you want to use, and then select **New team project**.  

	::: moniker range=">= azure-devops-2020"
	> [!div class="mx-imgBorder"]  
	> ![Create a project from the selected process](media/process/new-team-project-from-inherited-process-menu.png) 
	::: moniker-end
	::: moniker range="azure-devops-2019"
	> [!div class="mx-imgBorder"]  
	> ![Create a project from the selected process](media/process/add-new-team-project.png) 
	::: moniker-end

1. The Create new project page opens. Fill out the form. To learn more, see [Create a project](../../projects/create-project.md).

	::: moniker range=">= azure-devops-2020"
	> [!div class="mx-imgBorder"]  
	> ![Create new project form](media/process/create-test-project-sprint166.png) 
	::: moniker-end
	::: moniker range="azure-devops-2019"
	> [!div class="mx-imgBorder"]  
	> ![Create new project form](media/process/create-test-project.png) 
	::: moniker-end

2. Open the **Work>Work Items** page (user context) and choose **New Work Item** and select a WIT you customized. Here we choose **Bug**. 

	> [!div class="mx-imgBorder"]  
	> ![Work, Work Items Page, Add New Work Item, Bug](media/process/add-custom-field-verify-bug.png) 

3. Verify that the field(s) you added appear on the form. Note that the :::image type="icon" source="../../../media/icons/required-icon.png" border="false"::: (exclamation mark) icon indicates the field is required.  

<a id="test-import-export-process" />

### Create a test organization and import/export your process

You can also use the following steps to verify the customizations you've made to an inherited process. 
 
1. Create a test organization.  
2. Use the [import/export process tool](https://github.com/Microsoft/process-migrator) to copy the process to the test organization.  
3. Verify the process customizations in the test organization.   
4. Use the import/export process tool again to import the modified process to the production organization.  


[!INCLUDE [temp](../includes/change-project-to-inherited-process.md)] 


<a id="process-rest-api">  </a>

## Programmatically work with processes 

You can get, create, update, and delete processes defined for an organization using the [REST API, Processes](/rest/api/azure/devops/processes/processes/list).

## Related articles

Keep in mind that all projects that reference the inherited process that you're customizing automatically updates to contain the modifications you make.

To customize a single project, always start by [creating an inherited process and changing the project to use that process](manage-process.md). Then, all the customizations that you make to the inherited process automatically appear for the project you migrated.  

See also: 
- [Work tracking object limits](object-limits.md)
- [What is an inherited process?](inheritance-process-model.md) 

<!---
For example, the following image shows the work item form layout for the Bug WIT. From this page, you can add fields, groups, pages, and custom controls. To modify the workflow, you click **States**.

<img src="media/process/cprocess-intro.png" alt="Admin context, Process, Work item types, bug type, layout tab" /> 
-->
