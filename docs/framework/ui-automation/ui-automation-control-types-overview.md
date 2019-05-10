---
title: Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: e92d3248d02ef30e9a2bea296efa80408ee3351f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652190"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="42eae-102">Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="42eae-102">UI Automation Control Types Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="42eae-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="42eae-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="42eae-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="42eae-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="42eae-105">-Steuerelementtypen sind allgemein bekannte Bezeichner, die die Art eines bestimmten Steuerelements angeben, z. B. Kombinationsfeld oder Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="42eae-105">control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="42eae-106">Mit einem solchen Bezeichner können Geräte mit Hilfstechnologie leichter bestimmen, welche Steuerelementtypen in der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] verfügbar sind, und wie mit den Steuerelementen zu interagieren ist.</span><span class="sxs-lookup"><span data-stu-id="42eae-106">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="42eae-107">Anforderungen für Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="42eae-107">UI Automation Control Type Requisites</span></span>  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="42eae-108">-Steuerelementtypen geben eine Reihe von Bedingungen vor, die Anbieter erfüllen müssen.</span><span class="sxs-lookup"><span data-stu-id="42eae-108">control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="42eae-109">Wenn diese Bedingungen erfüllt sind, kann das Steuerelement den bestimmten Steuerelementtypnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="42eae-109">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="42eae-110">Für jeden Steuerelementtyp gibt es die folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="42eae-110">Each control type has conditions for the following:</span></span>  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="42eae-111">-Steuerelementmuster: Welche Steuerelementmuster müssen unterstützt, welche sind optional und welche dürfen vom Steuerelement nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="42eae-111">control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="42eae-112">-Eigenschaftswerte: Welche Eigenschaftswerte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42eae-112">property values—which property values are supported.</span></span>  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="42eae-113">-Struktur: Die erforderliche [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="42eae-113">tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="42eae-114">Wenn ein Steuerelement die Bedingungen für einen bestimmten Steuerelementtyp erfüllt, wird dieser Steuerelementtyp durch den <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> -Eigenschaftswert angegeben.</span><span class="sxs-lookup"><span data-stu-id="42eae-114">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="42eae-115">Aktuelle Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="42eae-115">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="42eae-116">Die folgende Liste enthält die aktuellen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen:</span><span class="sxs-lookup"><span data-stu-id="42eae-116">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
- [<span data-ttu-id="42eae-117">Benutzeroberflächenautomatisierungs-Unterstützung für den Schaltflächen-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-117">UI Automation Support for the Button Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
- [<span data-ttu-id="42eae-118">Benutzeroberflächenautomatisierungs-Unterstützung für den Kalender-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-118">UI Automation Support for the Calendar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
- [<span data-ttu-id="42eae-119">Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-119">UI Automation Support for the CheckBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
- [<span data-ttu-id="42eae-120">Benutzeroberflächenautomatisierungs-Unterstützung für den ComboBox-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-120">UI Automation Support for the ComboBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
- [<span data-ttu-id="42eae-121">Benutzeroberflächenautomatisierungs-Unterstützung für den DataGrid-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-121">UI Automation Support for the DataGrid Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
- [<span data-ttu-id="42eae-122">Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-122">UI Automation Support for the DataItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
- [<span data-ttu-id="42eae-123">Benutzeroberflächenautomatisierungs-Unterstützung für den Dokumentsteuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-123">UI Automation Support for the Document Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
- [<span data-ttu-id="42eae-124">Benutzeroberflächenautomatisierungs-Unterstützung für den Bearbeitungssteuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-124">UI Automation Support for the Edit Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
- [<span data-ttu-id="42eae-125">Benutzeroberflächenautomatisierungs-Unterstützung für den Gruppen-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-125">UI Automation Support for the Group Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
- [<span data-ttu-id="42eae-126">Benutzeroberflächenautomatisierungs-Unterstützung für den Header-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-126">UI Automation Support for the Header Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
- [<span data-ttu-id="42eae-127">Benutzeroberflächenautomatisierungs-Unterstützung für den HeaderItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-127">UI Automation Support for the HeaderItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
- [<span data-ttu-id="42eae-128">Benutzeroberflächenautomatisierungs-Unterstützung für den Link-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-128">UI Automation Support for the Hyperlink Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [<span data-ttu-id="42eae-129">Benutzeroberflächenautomatisierungs-Unterstützung für den Bild-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-129">UI Automation Support for the Image Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
- [<span data-ttu-id="42eae-130">Benutzeroberflächenautomatisierungs-Unterstützung für den Listen-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-130">UI Automation Support for the List Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
- [<span data-ttu-id="42eae-131">Benutzeroberflächenautomatisierungs-Unterstützung für den ListItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-131">UI Automation Support for the ListItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
- [<span data-ttu-id="42eae-132">Benutzeroberflächenautomatisierungs-Unterstützung für den Menü-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-132">UI Automation Support for the Menu Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
- [<span data-ttu-id="42eae-133">Benutzeroberflächenautomatisierungs-Unterstützung für den MenuBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-133">UI Automation Support for the MenuBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
- [<span data-ttu-id="42eae-134">Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-134">UI Automation Support for the MenuItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
- [<span data-ttu-id="42eae-135">Benutzeroberflächenautomatisierungs-Unterstützung für den Bereich-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-135">UI Automation Support for the Pane Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
- [<span data-ttu-id="42eae-136">Benutzeroberflächenautomatisierungs-Unterstützung für den ProgressBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-136">UI Automation Support for the ProgressBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
- [<span data-ttu-id="42eae-137">Benutzeroberflächenautomatisierungs-Unterstützung für den RadioButton-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-137">UI Automation Support for the RadioButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [<span data-ttu-id="42eae-138">Benutzeroberflächenautomatisierungs-Unterstützung für den ScrollBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-138">UI Automation Support for the ScrollBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [<span data-ttu-id="42eae-139">Benutzeroberflächenautomatisierungs-Unterstützung für den Separator-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-139">UI Automation Support for the Separator Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
- [<span data-ttu-id="42eae-140">Benutzeroberflächenautomatisierungs-Unterstützung für den Schieberegler-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-140">UI Automation Support for the Slider Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
- [<span data-ttu-id="42eae-141">Benutzeroberflächenautomatisierungs-Unterstützung für den Drehfeld-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-141">UI Automation Support for the Spinner Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
- [<span data-ttu-id="42eae-142">Benutzeroberflächenautomatisierungs-Unterstützung für den SplitButton-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-142">UI Automation Support for the SplitButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [<span data-ttu-id="42eae-143">Benutzeroberflächenautomatisierungs-Unterstützung für den StatusBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-143">UI Automation Support for the StatusBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
- [<span data-ttu-id="42eae-144">Benutzeroberflächenautomatisierungs-Unterstützung für den Registerkarten-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-144">UI Automation Support for the Tab Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
- [<span data-ttu-id="42eae-145">Benutzeroberflächenautomatisierungs-Unterstützung für den TabItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-145">UI Automation Support for the TabItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
- [<span data-ttu-id="42eae-146">Benutzeroberflächenautomatisierungs-Unterstützung für den Tabellen-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-146">UI Automation Support for the Table Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
- [<span data-ttu-id="42eae-147">Benutzeroberflächenautomatisierungs-Unterstützung für den Text-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-147">UI Automation Support for the Text Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
- [<span data-ttu-id="42eae-148">Benutzeroberflächenautomatisierungs-Unterstützung für den Ziehpunkt-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-148">UI Automation Support for the Thumb Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
- [<span data-ttu-id="42eae-149">Benutzeroberflächenautomatisierungs-Unterstützung für den TitleBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-149">UI Automation Support for the TitleBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
- [<span data-ttu-id="42eae-150">Benutzeroberflächenautomatisierungs-Unterstützung für den ToolBar-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-150">UI Automation Support for the ToolBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
- [<span data-ttu-id="42eae-151">Benutzeroberflächenautomatisierungs-Unterstützung für den ToolTip-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-151">UI Automation Support for the ToolTip Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
- [<span data-ttu-id="42eae-152">Benutzeroberflächenautomatisierungs-Unterstützung für den Struktur-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-152">UI Automation Support for the Tree Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
- [<span data-ttu-id="42eae-153">Benutzeroberflächenautomatisierungs-Unterstützung für den TreeItem-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-153">UI Automation Support for the TreeItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
- [<span data-ttu-id="42eae-154">Benutzeroberflächenautomatisierungs-Unterstützung für den Fenster-Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="42eae-154">UI Automation Support for the Window Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="42eae-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42eae-155">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
