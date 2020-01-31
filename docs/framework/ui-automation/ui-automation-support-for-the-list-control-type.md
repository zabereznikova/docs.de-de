---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den Listen-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- control types, List
- List control type
- UI Automation, List control type
ms.assetid: 0e959fcb-50f2-413b-948d-7167d279bc11
ms.openlocfilehash: 17c0116ba6610ef28e873696bbf3162175bc0601
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778609"
---
# <a name="ui-automation-support-for-the-list-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den Listen-Steuerelementtyp
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „List“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Der Steuerelementtyp „List“ bietet eine Möglichkeit zum Organisieren von unstrukturierten Elementgruppen und ermöglicht dem Benutzer, eines oder mehrere der Elemente auszuwählen. Der Steuerelementtyp „List“ ist hinsichtlich der Typen, die er als untergeordnete Elemente enthalten kann, nur wenig eingeschränkt. Dadurch können Benutzeroberflächenautomatisierungs-Anbieter bekannte Elemente für Auswahlcontainer unterstützen.  
  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Anforderungen in den folgenden Abschnitten gelten für alle Steuerelemente, die den Steuerelement Typ "List" implementieren, egal ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 oder Windows Forms. Ein Beispiel für Steuerelemente, die den Steuerelementtyp „List“ implementieren, sind Listencontainer-Steuerelemente.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die beiden Ansichten der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Listensteuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. In der Steuerelementansicht sind nur Steuerelemente enthalten. In der Inhaltsansicht werden redundante Informationen aus der Struktur entfernt. Ein Textsteuerelement zum Beschriften eines Kombinationsfeld wird beispielsweise als `ComboBox NameProperty`verfügbar gemacht. Da das Textsteuerelement so bereits in der Steuerelementansicht verfügbar gemacht wird, ist es nicht erforderlich, das Element noch einmal verfügbar zu machen. Es wird daher aus der Inhaltsansicht entfernt. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|Enthält die Elemente, die Steuerelementen entsprechen.|Entfernt redundante Informationen aus der Struktur, sodass Hilfstechnologien den kleinsten Satz von für den Endbenutzer sinnvollen Informationen verwenden.|  
|Liste<br /><br /> -DataItem (0 oder mehr)<br />-ListItem (0 oder mehr)<br />-Group (0 oder mehr)<br />-ScrollBar (0, 1 oder 2)|Liste<br /><br /> -DataItem (0 oder mehr)<br />-ListItem (0 oder mehr)<br />-Group (0 oder mehr)|  
  
 Die Steuerelementansicht für ein Steuerelement, das den Steuerelementtyp „List“ implementiert (z. B. ein Listensteuerelement), umfasst die folgenden Elemente:  
  
- 0 (null) oder mehr Elemente innerhalb des Listen Steuer Elements (Elemente können auf dem Listenelement-oder Datenelement-Steuer Elementtyp basieren).
  
- 0 (null) oder mehr Gruppen Steuerelemente in einem Listen Steuerelement.
  
- NULL, ein oder zwei ScrollBar-Steuerelemente.
  
Die Inhaltsansicht eines Steuerelements, das den Steuerelementtyp „List“ implementiert (z. B. ein Listensteuerelement), besteht aus folgenden Elementen:  
  
- 0 (null) oder mehr Elemente innerhalb des Listen Steuer Elements (Elemente können auf dem Listenelement-oder Datenelement-Steuer Elementtyp basieren).
  
- NULL oder mehr Gruppen innerhalb des Listen Steuer Elements.

Ein Listensteuerelement darf keine Elemente enthalten, die andere hierarchische Beziehungen als die Gruppierung aufweisen. Wenn die Elemente in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur über untergeordnete Elemente verfügen, sollte der Listencontainer auf dem Steuerelementtyp „Tree“ basieren.  
  
 Die innerhalb des Listensteuerelements auswählbaren Elemente sind über die Nachfolgerelemente in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur des Listensteuerelements verfügbar. Alle Elemente innerhalb des Listensteuerelements müssen zur gleichen Auswahlgruppe gehören. Die auswählbaren Elemente in der Liste sollten als ListItem-Steuerelementtypen (und nicht als DataItem-Steuerelementtypen) verfügbar gemacht werden.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für Listensteuerelemente besonders relevant sind. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie unter [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|{2&gt;Wert&lt;2}|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Wenn das Listensteuerelement über einen klickbaren Punkt verfügt (ein Punkt, auf den geklickt werden kann, damit die Liste den Fokus erhält), muss dieser Punkt durch diese Eigenschaft verfügbar gemacht werden.<br /><br /> Wenn der Wert der `IsOffScreen`-Eigenschaft true ist, wird die <xref:System.Windows.Automation.NoClickablePointException> ausgelöst.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Der Wert der Eigenschaft „Name“ eines Listensteuerelements sollte die Kategorie der Optionen vermitteln, die dem Benutzer zur Auswahl zur Verfügung stehen. Diese Eigenschaft ruft ihren Namen in der Regel aus einer statischen Textbezeichnung ab. Wenn keine statische Textbezeichnung vorhanden ist, muss der Anwendungsentwickler einen Wert für die Eigenschaft „Name“ verfügbar machen.<br /><br /> Nur wenn das Steuerelement innerhalb der Teilstruktur eines anderen Steuerelements verwendet wird, ist diese Eigenschaft für Listensteuerelemente nicht erforderlich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Siehe Hinweise.|Wenn eine statische Textbezeichnung vorhanden ist, muss diese Eigenschaft einen Verweis auf das entsprechende Steuerelement verfügbar machen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Liste|Dieser Wert ist für alle Benutzeroberflächen-Frameworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Liste“|Lokalisierte Zeichenfolge für den Steuerelementtyp „List“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Strukturelement-Steuerelement ist stets in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Strukturelement-Steuerelement ist stets in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Wenn der Container Tastatureingaben akzeptieren kann, sollte dieser Eigenschaftswert „True“ sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Siehe Hinweise.|Der Hilfetext für Listensteuerelemente sollte erläutern, warum der Benutzer aufgefordert wird, aus einer Liste von Optionen auszuwählen. Beispiel: „Durch Auswählen eines Elements in dieser Liste wird die Anzeigeauflösung für den Bildschirm festgelegt.“|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster und -Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von allen Listensteuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster/Mustereigenschaft|Unterstützung/Wert|Hinweise|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Erforderlich|Alle Steuerelemente, die den Steuerelementtyp „List“ unterstützen, müssen `ISelectionProvider` implementieren, wenn der Auswahlzustand der im Steuerelement enthaltenen Elemente beibehalten wird. Wenn die Elemente innerhalb des Containers nicht auswählbar sind, muss der Steuerelementtyp Steuerelementtyp „Group“ verwendet werden.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Variabel|In einem Listensteuerelement muss nicht immer ein Element ausgewählt sein.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Variabel|Listensteuerelemente können Container für Einfach- oder Mehrfachauswahl sein.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Variabel|Implementieren Sie dieses Steuerelementmuster, wenn Elemente im Container bildlauffähig sind.|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Variabel|Implementieren Sie dieses Muster, wenn die Rasternavigation auf Grundlage einzelner Elemente zur Verfügung stehen soll.|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Variabel|Implementieren Sie dieses Steuerelementmuster, wenn das Steuerelement mehrere Ansichten für die Elemente im Container unterstützen soll.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Nie|Für den Steuerelementtyp „List“ wird`ITableProvider` nie unterstützt. Wenn das Steuerelement dieses Steuerelementmuster unterstützen soll, sollte das Steuerelement auf dem Steuerelementtyp „DataGrid“ basieren.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Listensteuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung/Wert|Hinweise|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Variabel|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.List>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
