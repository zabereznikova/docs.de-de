---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den ListItem-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- control types, List
- List Item control type
- UI Automation, List Item control type
ms.assetid: 34f533bf-fc14-4e78-8fee-fb7107345fab
ms.openlocfilehash: 4b7c3b6bbdc38227871ea020047bc21987b18ee9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446715"
---
# <a name="ui-automation-support-for-the-listitem-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den ListItem-Steuerelementtyp
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den <xref:System.Windows.Automation.ControlType.ListItem> -Steuerelementtyp. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Ein Beispiel für Steuerelemente, die den Steuerelementtyp „ListItem“ implementieren, sind Listenelement-Steuerelemente.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „ListItem“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Listensteuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgende Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Listenelement-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|ListItem<br /><br /> -Image (0 oder mehr)<br />-Text (0 oder mehr)<br />-Edit (0 oder mehr)|ListItem|  
  
 Die untergeordneten Elemente eines Listenelement-Steuerelements innerhalb der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur müssen immer "0" sein. Wenn die Struktur des Steuer Elements darin besteht, dass andere Elemente unterhalb des Listen Elements enthalten sind, sollten Sie die Anforderungen an die [Benutzeroberflächenautomatisierungs-Unterstützung für den Steuer Elementtyp "TreeItem-Steuer Elementtyp](ui-automation-support-for-the-treeitem-control-type.md) " befolgen.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für Listenelement-Steuerelemente besonders relevant sind. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie unter [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft sollte den Bereich des Bilds und den Textinhalt des Listenelements enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Variabel|Wenn das Listensteuerelement über einen klickbaren Punkt verfügt (ein Punkt, auf den geklickt werden kann, damit die Liste den Fokus erhält), muss dieser Punkt durch diese Eigenschaft verfügbar gemacht werden. Wenn das Listensteuerelement vollständig von Nachfolgerlistenelementen abgedeckt ist, wird eine <xref:System.Windows.Automation.NoClickablePointException> ausgelöst, um anzuzeigen, dass der Client von einem Element innerhalb des Listensteuerelements einen klickbaren Punkt anfordern muss.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Der Wert der Eigenschaft „Name“ eines Listenelement-Steuerelements wird vom Textinhalt des Elements abgeleitet.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Siehe Hinweise.|Wenn eine statische Textbezeichnung vorhanden ist, muss diese Eigenschaft einen Verweis auf das entsprechende Steuerelement verfügbar machen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ListItem|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Listenelement“|Lokalisierte Zeichenfolge für den Steuerelementtyp „ListItem“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Strukturelement-Steuerelement ist stets in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Strukturelement-Steuerelement ist stets in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Wenn der Container Tastatureingaben akzeptieren kann, sollte dieser Eigenschaftswert „True“ sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|""|Im Hilfetext für Listensteuerelemente sollte erklärt werden, warum der Benutzer aufgefordert wird, eine Auswahl aus einer Liste von Optionen zu treffen. Hierbei handelt es sich in der Regel um dieselben Informationen, die durch ein QuickInfo angezeigt werden. Beispiel: „Wählen Sie ein Element aus, um die Anzeigeauflösung für den Bildschirm festzulegen.“|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|Variabel|Diese Eigenschaft sollte für Listenelement-Steuerelemente verfügbar gemacht werden, die ein zugrunde liegendes Objekt darstellen. Bei diesen Listenelement-Steuerelementen ist dem Steuerelement normalerweise ein Symbol zugeordnet, das Benutzer mit dem zugrunde liegenden Objekt assoziieren.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Variabel|Diese Eigenschaft muss einen Wert zurückgeben, der angibt, ob das Listenelement innerhalb des übergeordneten Containers, der das Scroll-Steuerelementmuster implementiert, derzeit durch einen Bildlauf angezeigt wird.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von allen Listenelement-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster|Unterstützungswert|Hinweise|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Ja|Ein Listenelement-Steuerelement muss dieses Steuerelementmuster implementieren. Dadurch kann die Auswahl eines Listenelement-Steuerelements angezeigt werden.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Variabel|Wenn das Listenelement in einem bildlauffähigen Container enthalten ist, muss dieses Steuerelementmuster implementiert werden.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Variabel|Wenn das Listenelement überprüfbar ist und die Aktion den Auswahlzustand nicht ändert, muss dieses Steuerelementmuster implementiert werden.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Variabel|Wenn das Element so geändert werden kann, dass Informationen angezeigt oder ausgeblendet werden, muss dieses Steuerelementmuster implementiert werden.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Variabel|Wenn das Element bearbeitet werden kann, muss dieses Steuerelementmuster implementiert werden. Durch Änderungen am Listenelement-Steuerelement werden die Werte von <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>und <xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>geändert|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Variabel|Wenn innerhalb des Listencontainers die räumliche Navigation zwischen Elementen unterstützt wird und der Container in Zeilen und Spalten aufgeteilt ist, muss das GridItem-Steuerelementmuster implementiert werden.|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Variabel|Wenn für das Element ein Befehl existiert, der für dieses durchgeführt werden kann (abgesehen von der Auswahl), muss dieses Steuerelementmuster implementiert werden. Dies ist normalerweise eine Aktion, die dem Doppelklicken auf das Listenelement-Steuerelement zugeordnet wird. Beispiele wären das Starten eines Dokuments von Microsoft Windows Explorer oder das Abspielen einer Musikdatei in Microsoft Windows Media Player.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Listenelementen unterstützt werden müssen. Weitere Informationen zu [UI Automation Events Overview](ui-automation-events-overview.md)-Ereignissen finden Sie unter  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützungswert|Hinweise|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Variabel|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.ListItem>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
