---
title: "Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c1a424f05f2d57f773e8367e102f553d69b7dc22
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="80042-102">Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="80042-102">UI Automation Control Types Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="80042-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="80042-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="80042-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="80042-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]<span data-ttu-id="80042-105"> -Steuerelementtypen sind allgemein bekannte Bezeichner, die die Art eines bestimmten Steuerelements angeben, z. B. Kombinationsfeld oder Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="80042-105"> control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="80042-106">Mit einem solchen Bezeichner können Geräte mit Hilfstechnologie leichter bestimmen, welche Steuerelementtypen in der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] verfügbar sind, und wie mit den Steuerelementen zu interagieren ist.</span><span class="sxs-lookup"><span data-stu-id="80042-106">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="80042-107">Anforderungen für Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="80042-107">UI Automation Control Type Requisites</span></span>  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]<span data-ttu-id="80042-108"> -Steuerelementtypen geben eine Reihe von Bedingungen vor, die Anbieter erfüllen müssen.</span><span class="sxs-lookup"><span data-stu-id="80042-108"> control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="80042-109">Wenn diese Bedingungen erfüllt sind, kann das Steuerelement den bestimmten Steuerelementtypnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="80042-109">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="80042-110">Für jeden Steuerelementtyp gibt es die folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="80042-110">Each control type has conditions for the following:</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="80042-111"> -Steuerelementmuster: Welche Steuerelementmuster müssen unterstützt, welche sind optional und welche dürfen vom Steuerelement nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="80042-111"> control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="80042-112"> -Eigenschaftswerte: Welche Eigenschaftswerte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80042-112"> property values—which property values are supported.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="80042-113"> -Struktur: Die erforderliche [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="80042-113"> tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="80042-114">Wenn ein Steuerelement die Bedingungen für einen bestimmten Steuerelementtyp erfüllt, wird dieser Steuerelementtyp durch den <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> -Eigenschaftswert angegeben.</span><span class="sxs-lookup"><span data-stu-id="80042-114">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="80042-115">Aktuelle Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="80042-115">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="80042-116">Die folgende Liste enthält die aktuellen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen:</span><span class="sxs-lookup"><span data-stu-id="80042-116">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
-   [<span data-ttu-id="80042-117">Benutzeroberflächenautomatisierungs-Unterstützung für das Button-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-117">UI Automation Support for the Button Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [<span data-ttu-id="80042-118">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Calendar"</span><span class="sxs-lookup"><span data-stu-id="80042-118">UI Automation Support for the Calendar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [<span data-ttu-id="80042-119">Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-119">UI Automation Support for the CheckBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [<span data-ttu-id="80042-120">Benutzeroberflächenautomatisierungs-Unterstützung für den ComboBox-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-120">UI Automation Support for the ComboBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [<span data-ttu-id="80042-121">Benutzeroberflächenautomatisierungs-Unterstützung für den DataGrid-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-121">UI Automation Support for the DataGrid Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [<span data-ttu-id="80042-122">Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-122">UI Automation Support for the DataItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [<span data-ttu-id="80042-123">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Document"</span><span class="sxs-lookup"><span data-stu-id="80042-123">UI Automation Support for the Document Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [<span data-ttu-id="80042-124">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Edit"</span><span class="sxs-lookup"><span data-stu-id="80042-124">UI Automation Support for the Edit Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [<span data-ttu-id="80042-125">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Group"</span><span class="sxs-lookup"><span data-stu-id="80042-125">UI Automation Support for the Group Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [<span data-ttu-id="80042-126">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Header"</span><span class="sxs-lookup"><span data-stu-id="80042-126">UI Automation Support for the Header Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [<span data-ttu-id="80042-127">Benutzeroberflächenautomatisierungs-Unterstützung für den HeaderItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-127">UI Automation Support for the HeaderItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [<span data-ttu-id="80042-128">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Hyperlink"</span><span class="sxs-lookup"><span data-stu-id="80042-128">UI Automation Support for the Hyperlink Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [<span data-ttu-id="80042-129">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Image"</span><span class="sxs-lookup"><span data-stu-id="80042-129">UI Automation Support for the Image Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [<span data-ttu-id="80042-130">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "List"</span><span class="sxs-lookup"><span data-stu-id="80042-130">UI Automation Support for the List Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [<span data-ttu-id="80042-131">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "ListItem" "</span><span class="sxs-lookup"><span data-stu-id="80042-131">UI Automation Support for the ListItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [<span data-ttu-id="80042-132">Benutzeroberflächenautomatisierungs-Unterstützung für den Menü-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-132">UI Automation Support for the Menu Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [<span data-ttu-id="80042-133">Benutzeroberflächenautomatisierungs-Unterstützung für den MenuBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-133">UI Automation Support for the MenuBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [<span data-ttu-id="80042-134">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "MenuItem" "</span><span class="sxs-lookup"><span data-stu-id="80042-134">UI Automation Support for the MenuItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [<span data-ttu-id="80042-135">Benutzeroberflächenautomatisierungs-Unterstützung für den Pane-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-135">UI Automation Support for the Pane Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [<span data-ttu-id="80042-136">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "ProgressBar" "</span><span class="sxs-lookup"><span data-stu-id="80042-136">UI Automation Support for the ProgressBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [<span data-ttu-id="80042-137">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "RadioButton" "</span><span class="sxs-lookup"><span data-stu-id="80042-137">UI Automation Support for the RadioButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [<span data-ttu-id="80042-138">Benutzeroberflächenautomatisierungs-Unterstützung für den ScrollBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-138">UI Automation Support for the ScrollBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [<span data-ttu-id="80042-139">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Separator"</span><span class="sxs-lookup"><span data-stu-id="80042-139">UI Automation Support for the Separator Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [<span data-ttu-id="80042-140">Benutzeroberflächenautomatisierungs-Unterstützung für den Slider-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-140">UI Automation Support for the Slider Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [<span data-ttu-id="80042-141">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Spinner"</span><span class="sxs-lookup"><span data-stu-id="80042-141">UI Automation Support for the Spinner Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [<span data-ttu-id="80042-142">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "SplitButton" "</span><span class="sxs-lookup"><span data-stu-id="80042-142">UI Automation Support for the SplitButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [<span data-ttu-id="80042-143">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "StatusBar" "</span><span class="sxs-lookup"><span data-stu-id="80042-143">UI Automation Support for the StatusBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [<span data-ttu-id="80042-144">Benutzeroberflächenautomatisierungs-Unterstützung für den Tab-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-144">UI Automation Support for the Tab Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [<span data-ttu-id="80042-145">Benutzeroberflächenautomatisierungs-Unterstützung für den TabItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-145">UI Automation Support for the TabItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [<span data-ttu-id="80042-146">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Table"</span><span class="sxs-lookup"><span data-stu-id="80042-146">UI Automation Support for the Table Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [<span data-ttu-id="80042-147">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Text"</span><span class="sxs-lookup"><span data-stu-id="80042-147">UI Automation Support for the Text Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [<span data-ttu-id="80042-148">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Thumb"</span><span class="sxs-lookup"><span data-stu-id="80042-148">UI Automation Support for the Thumb Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [<span data-ttu-id="80042-149">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "TitleBar" "</span><span class="sxs-lookup"><span data-stu-id="80042-149">UI Automation Support for the TitleBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [<span data-ttu-id="80042-150">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "ToolBar"</span><span class="sxs-lookup"><span data-stu-id="80042-150">UI Automation Support for the ToolBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [<span data-ttu-id="80042-151">Benutzeroberflächenautomatisierungs-Unterstützung für den ToolTip-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="80042-151">UI Automation Support for the ToolTip Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [<span data-ttu-id="80042-152">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Tree"</span><span class="sxs-lookup"><span data-stu-id="80042-152">UI Automation Support for the Tree Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [<span data-ttu-id="80042-153">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "TreeItem" "</span><span class="sxs-lookup"><span data-stu-id="80042-153">UI Automation Support for the TreeItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [<span data-ttu-id="80042-154">Benutzeroberflächenautomatisierungs-Unterstützung für den Steuerelementtyp "Window"</span><span class="sxs-lookup"><span data-stu-id="80042-154">UI Automation Support for the Window Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="80042-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80042-155">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType>
