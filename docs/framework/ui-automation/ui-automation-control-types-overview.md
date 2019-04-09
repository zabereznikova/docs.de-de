---
title: Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: e9cbff2ec6496cabe827e075b737a8c6f16fee93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147718"
---
# <a name="ui-automation-control-types-overview"></a>Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen sind allgemein bekannte Bezeichner, die verwendet werden können, um anzugeben, welche Art von Steuerelement ein bestimmtes Element, z. B. ein Kombinationsfeld oder Schaltfläche darstellt.  
  
 Mit einem solchen Bezeichner können Geräte mit Hilfstechnologie leichter bestimmen, welche Steuerelementtypen in der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] verfügbar sind, und wie mit den Steuerelementen zu interagieren ist.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a>Anforderungen für Steuerelementtypen der Benutzeroberflächenautomatisierung  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen geben eine Reihe von Bedingungen, die Anbieter erfüllen müssen. Wenn diese Bedingungen erfüllt sind, kann das Steuerelement den bestimmten Steuerelementtypnamen verwenden. Für jeden Steuerelementtyp gibt es die folgenden Bedingungen:  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Steuerelementmuster: welche Steuerelementmuster müssen unterstützt werden, welches Steuerelement sind optional und welche Steuerelementmuster müssen nicht vom Steuerelement unterstützt werden.  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaftswerte: welche Eigenschaftswerte werden unterstützt.  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur, die erforderlichen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur für das Steuerelement.  
  
 Wenn ein Steuerelement die Bedingungen für einen bestimmten Steuerelementtyp erfüllt, wird dieser Steuerelementtyp durch den <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> -Eigenschaftswert angegeben.  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a>Aktuelle Steuerelementtypen der Benutzeroberflächenautomatisierung  
 Die folgende Liste enthält die aktuellen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen:  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Schaltflächen-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Calendar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den ComboBox-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den DataGrid-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Document-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Edit-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Group-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Header-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den HeaderItem-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Hyperlink-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Bild-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den List-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den ListItem-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Menü-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den MenuBar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Pane-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den ProgressBar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den RadioButton-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den ScrollBar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Separator-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Slider-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Spinner-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den SplitButton-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den StatusBar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Tab-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den TabItem-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Table-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Text-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Thumb-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [Benutzeroberflächenautomatisierung-Unterstützung für den TitleBar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den ToolBar-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den ToolTip-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Struktur-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den TreeItem-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung für den Window-Steuerelementtyp](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType>
