---
title: Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: ec2dd3635f09144985df278be1d53ead675d3080
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442629"
---
# <a name="ui-automation-control-types-overview"></a>Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen sind allgemein bekannte Bezeichner, die die Art eines bestimmten Steuerelements angeben, z. B. Kombinationsfeld oder Schaltfläche.  
  
 Mit einem solchen Bezeichner können Geräte mit Hilfstechnologie leichter bestimmen, welche Steuerelementtypen in der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] verfügbar sind, und wie mit den Steuerelementen zu interagieren ist.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a>Anforderungen für Steuerelementtypen der Benutzeroberflächenautomatisierung  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen geben eine Reihe von Bedingungen vor, die Anbieter erfüllen müssen. Wenn diese Bedingungen erfüllt sind, kann das Steuerelement den bestimmten Steuerelementtypnamen verwenden. Für jeden Steuerelementtyp gibt es die folgenden Bedingungen:  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster: Welche Steuerelementmuster müssen unterstützt, welche sind optional und welche dürfen vom Steuerelement nicht unterstützt werden.  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte: Welche Eigenschaftswerte werden unterstützt.  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur: Die erforderliche [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für das Steuerelement.  
  
 Wenn ein Steuerelement die Bedingungen für einen bestimmten Steuerelementtyp erfüllt, wird dieser Steuerelementtyp durch den <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> -Eigenschaftswert angegeben.  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a>Aktuelle Steuerelementtypen der Benutzeroberflächenautomatisierung  
 Die folgende Liste enthält die aktuellen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementtypen:  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Schaltflächen-Steuerelementtyp](ui-automation-support-for-the-button-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Kalender-Steuerelementtyp](ui-automation-support-for-the-calendar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelementtyp](ui-automation-support-for-the-checkbox-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den ComboBox-Steuerelementtyp](ui-automation-support-for-the-combobox-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den DataGrid-Steuerelementtyp](ui-automation-support-for-the-datagrid-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp](ui-automation-support-for-the-dataitem-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Dokumentsteuerelementtyp](ui-automation-support-for-the-document-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Bearbeitungssteuerelementtyp](ui-automation-support-for-the-edit-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Gruppen-Steuerelementtyp](ui-automation-support-for-the-group-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Header-Steuerelementtyp](ui-automation-support-for-the-header-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den HeaderItem-Steuerelementtyp](ui-automation-support-for-the-headeritem-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Link-Steuerelementtyp](ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Bild-Steuerelementtyp](ui-automation-support-for-the-image-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Listen-Steuerelementtyp](ui-automation-support-for-the-list-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den ListItem-Steuerelementtyp](ui-automation-support-for-the-listitem-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Menü-Steuerelementtyp](ui-automation-support-for-the-menu-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den MenuBar-Steuerelementtyp](ui-automation-support-for-the-menubar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp](ui-automation-support-for-the-menuitem-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Bereich-Steuerelementtyp](ui-automation-support-for-the-pane-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den ProgressBar-Steuerelementtyp](ui-automation-support-for-the-progressbar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den RadioButton-Steuerelementtyp](ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den ScrollBar-Steuerelementtyp](ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Separator-Steuerelementtyp](ui-automation-support-for-the-separator-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Schieberegler-Steuerelementtyp](ui-automation-support-for-the-slider-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Drehfeld-Steuerelementtyp](ui-automation-support-for-the-spinner-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den SplitButton-Steuerelementtyp](ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den StatusBar-Steuerelementtyp](ui-automation-support-for-the-statusbar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Registerkarten-Steuerelementtyp](ui-automation-support-for-the-tab-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den TabItem-Steuerelementtyp](ui-automation-support-for-the-tabitem-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Tabellen-Steuerelementtyp](ui-automation-support-for-the-table-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Text-Steuerelementtyp](ui-automation-support-for-the-text-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Ziehpunkt-Steuerelementtyp](ui-automation-support-for-the-thumb-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den TitleBar-Steuerelementtyp](ui-automation-support-for-the-titlebar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den ToolBar-Steuerelementtyp](ui-automation-support-for-the-toolbar-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den ToolTip-Steuerelementtyp](ui-automation-support-for-the-tooltip-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Struktur-Steuerelementtyp](ui-automation-support-for-the-tree-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den TreeItem-Steuerelementtyp](ui-automation-support-for-the-treeitem-control-type.md)  
  
- [Benutzeroberflächenautomatisierungs-Unterstützung für den Fenster-Steuerelementtyp](ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType>
