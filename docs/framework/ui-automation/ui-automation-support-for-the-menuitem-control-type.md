---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp
description: Informationen zur Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuer Elementtyp. Erlernen Sie die erforderliche Struktur, Eigenschaften, Steuerelement Muster und Ereignisse.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu Item
- Menu Item control type
- UI Automation, Menu Item control type
ms.assetid: 54bce311-3d23-40b9-ba90-1bdbdaf8fbba
ms.openlocfilehash: 248fdacee42c3a67c6c3b2d5792b774dfdc8408f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166022"
---
# <a name="ui-automation-support-for-the-menuitem-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).

Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „MenuItem“. Im Thema wird die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Struktur des Steuerelements beschrieben und werden die Eigenschaften sowie Steuerelementmuster angegeben, die für den Steuerelementtyp „MenuItem“ erforderlich sind.

Ein Menüsteuerelement ermöglicht die hierarchische Organisation von Elementen, die Befehlen und Ereignishandlern zugeordnet sind. In einer typischen Microsoft Windows-Anwendung enthält eine Menüleiste mehrere Menü Elemente (z. b. **Datei**, **Bearbeiten**und **Fenster**), und jedes Menü Element zeigt ein Menü an. Ein Menü enthält eine Sammlung von Menüelementen (z. B. **Neu**, **Öffnen**und **Schließen**), die erweitert werden können, um weitere Menüelemente anzuzeigen, oder auf die geklickt werden kann, um eine bestimmte Aktion auszuführen. Ein Menüelement kann in einem Menü, auf einer Menüleiste oder auf einer Symbolleiste gehostet werden.

In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „MenuItem“ erforderlich sind. Die- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Anforderungen gelten für alle Listen Steuerelemente, ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 oder Windows Forms.

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur

In der folgende Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Menüelement-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Steuerelementansicht|Inhaltsansicht|
|------------------|------------------|
|MenuItem „Hilfe“ (?)<br /><br /> <ul><li>Menü (Untermenü des Menüelements „Hilfe“)<br /><br /> <ul><li>MenuItem „Hilfethemen“</li><li>MenuItem „Info“</li></ul></li></ul>|MenuItem „Hilfe“ (?)<br /><br /> -MENUITEM "Hilfe Themen"<br />-MENUITEM "Info zu Notepad"|

Die Steuerelementansicht des MenuItem-Steuerelements verfügt über die oben gezeigte [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur. Beachten Sie, dass das **Hilfe** -Menü Element enthalten ist, um die Struktur in einem typischen Menü der unter Menühierarchie besser zu veranschaulichen.

Bei der Inhaltsansicht fehlt das Menü in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, da es dem Endbenutzer keine relevanten Informationen vermittelt.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für MenuItem-Steuerelemente besonders relevant sind. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).

|Eigenschaft|Wert|BESCHREIBUNG|
|--------------|-----------|-----------------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Das MenuItem-Steuerelement ist in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten und es wird mit einer Bezeichnung versehen.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Keine Bezeichnung.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|MenuItem|Dieser Wert ist für alle Benutzeroberflächen-Frameworks gleich.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Menüelement“|Lokalisierte Zeichenfolge für den Steuerelementtyp „MenuItem“.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Richtig|Das MenuItem-Steuerelement ist in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur nie enthalten.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Richtig|Das MenuItem-Steuerelement muss in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur immer enthalten sein.|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von allen MenuItem-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Steuerelementmustereigenschaft|Support|Notizen|
|------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Depends (Abhängig)|Wenn das Steuerelement erweitert oder reduziert werden kann, implementieren Sie <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.|
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Depends (Abhängig)|Wenn das Steuerelement eine einzelne Aktion oder einen Befehl ausführt, implementieren Sie <xref:System.Windows.Automation.Provider.IInvokeProvider>.|
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Depends (Abhängig)|Wenn das Steuerelement eine Option darstellt, die aktiviert oder deaktiviert werden kann, implementieren Sie <xref:System.Windows.Automation.Provider.IToggleProvider>.|
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Depends (Abhängig)|Wenn das Steuerelement für die Auswahl aus einer Liste von Optionen unter Menüelementen verwendet wird, implementieren Sie <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.|

<a name="UI_Automation_Events_for_Menu_Item"></a>

## <a name="ui-automation-events-for-menu-item"></a>Benutzeroberflächenautomatisierungs-Ereignisse für Menüelemente

In der folgenden Tabelle sind die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Ereignisse aufgeführt, die dem MenuItem-Steuerelement zugeordnet sind.

|Ereignis|Support|Erklärung|
|-----------|-------------|-----------------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depends (Abhängig)|Muss ausgelöst werden, wenn das Steuerelement Invoke-Steuerelementmuster unterstützt.|
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Muss ausgelöst werden, wenn das Steuerelement Toggle-Steuerelementmuster unterstützt.|
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Muss ausgelöst werden, wenn das Steuerelement „Expand Collapse“-Steuerelementmuster unterstützt.|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Depends (Abhängig)|Keine|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen MenuItem-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).

|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung/Wert|Hinweise|
|---------------------------------------------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depends (Abhängig)|Keine|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Depends (Abhängig)|Keine|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Depends (Abhängig)|Keine|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Depends (Abhängig)|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Keine|
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Keine|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|

<a name="Legacy_Issues"></a>

## <a name="legacy-issues"></a>Legacyprobleme

Ein Toggle-Muster wird nur unterstützt, wenn das Win32-Menü Element aktiviert ist und Programm gesteuert festgelegt werden kann, dass ein UMSCHALT Muster unterstützt wird. Da das Win32-Menü Element nicht verfügbar macht, ob es aktiviert werden kann, wird das Aufruf Muster unterstützt, wenn das Menü Element nicht aktiviert ist. Es wird eine Ausnahme gemacht, um Invoke-Muster immer zu unterstützen. Dies gilt auch für Menüelemente, die ausschließlich Toggle-Muster unterstützen sollten. Der Grund hierfür ist, dass Clients nicht irritiert werden sollen, wenn ein Element, das Invoke-Muster unterstützt hat (wenn das Menüelement nicht aktiviert ist), dieses Muster nicht mehr unterstützt, nachdem das Menüelement aktiviert wurde.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.ControlType.MenuItem>
- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
