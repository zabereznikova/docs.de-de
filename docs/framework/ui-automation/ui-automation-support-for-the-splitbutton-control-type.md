---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den SplitButton-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- Split Button control type
- control types, Split Button
- UI Automation, Split Button control type
ms.assetid: 14b05ccf-bcd8-4045-9bae-f7679cd98711
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 5b4bd79d9895a2868f9caf6ac4a2e67faef5f9c0
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266857"
---
# <a name="ui-automation-support-for-the-splitbutton-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den SplitButton-Steuerelementtyp
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „SplitButton“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Das Steuerelement für eine unterteilte Schaltfläche bietet die Möglichkeit, eine Aktion für ein Steuerelement auszuführen und das Steuerelement zu erweitern, um eine Liste mit anderen möglichen Aktionen, die ausgeführt werden können, anzuzeigen.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „SplitButton“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Steuerelemente für unterteilte Schaltflächen in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Steuerelemente für unterteilte Schaltflächen sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen über die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|SplitButton<br /><br /> <ul><li>Image (0 oder 1)</li><li>Text (0 oder 1)</li><li>Button (1 oder 2)<br /><br /> <ul><li>Menu (0 oder 1; erscheint als untergeordnetes Element von „Button“, das das ExpandCollapse-Muster unterstützt)</li><li>MenuItem (1:n)</li></ul></li></ul>|SplitButton<br /><br /> -MenuItem (1 bis viele)|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für Steuerelemente für unterteilte Schaltflächen besonders relevant sind. Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|"Zurück"|Der Name des Steuerelements für eine unterteilte Schaltfläche wird auf der Schaltfläche angezeigt.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Null|Steuerelemente für unterteilte Schaltflächen verfügen nicht über eine statische Textbezeichnung.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|SplitButton|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Unterteilte Schaltfläche“|Lokalisierte Zeichenfolge für den Steuerelementtyp „SplitButton“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Siehe Hinweise.|Der Hilfetext kann das Ergebnis der Aktivierung der unterteilten Schaltfläche angeben. Hierbei handelt es sich in der Regel um dieselben Informationen, die durch ein QuickInfo angezeigt werden.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Steuerelement für eine unterteilte Schaltfläche enthält Informationen für den Endbenutzer.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Steuerelement für eine unterteilte Schaltfläche ist für den Endbenutzer sichtbar.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von Steuerelementen für unterteilte Schaltflächen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster|Unterstützung|Hinweise|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Erforderlich|Steuerelemente für unterteilte Schaltflächen verfügen immer über eine Standardaktion, die Invoke zugeordnet ist.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Erforderlich|Steuerelemente für unterteilte Schaltflächen verfügen immer über die Fähigkeit, eine Liste von Optionen zu erweitern.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Steuerelementen für unterteilte Schaltflächen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung|Hinweise|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keiner|  
  
<a name="Split_Button_Control_Example"></a>   
## <a name="splitbutton-control-example"></a>Beispiel für ein SplitButton-Steuerelement  
 In der folgenden Abbildung sehen Sie einen SplitButton-Steuerelementtyp in einem DataGrid-Steuerelement.  
  
 ![Unterteilte Schaltfläche](../../../docs/framework/ui-automation/media/uiauto-splitbutton-detailed.gif "Uiauto_splitbutton_detailed")  
  
 Die Steuerelementansicht und die Inhaltsansicht der Benutzeroberflächenautomatisierungs-Struktur, die zum DataGrid- und zum SplitButton-Steuerelement gehören, werden unten dargestellt. Die Steuerelementmuster für jedes Automatisierungselement sind in Klammern aufgeführt.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Steuerelementansicht|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Inhaltsansicht|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|<ul><li>SplitButton „Name“ (Invoke, ExpandCollapse)</li><li>Button „Weitere Optionen“ (Invoke)<br /><br /> <ul><li>Menü</li><li>MenuItem</li><li>…</li></ul></li></ul>|<ul><li>SplitButton „Name“ (Invoke, ExpandCollapse)</li><li>Button „Weitere Optionen“ (Invoke)<br /><br /> <ul><li>Menü</li><li>MenuItem</li><li>…</li></ul></li></ul>|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Automation.ControlType.SplitButton>  
 [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
