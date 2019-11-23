---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den Calendar-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Calendar control type
- Calendar control type
- control types, Calendar
ms.assetid: e91a7393-a7f9-4838-a1a6-857438b24bc9
ms.openlocfilehash: df2466eb744e1d048f406b985867347a005709cc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441132"
---
# <a name="ui-automation-support-for-the-calendar-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den Calendar-Steuerelementtyp
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „Calendar“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte, Steuerelementmuster und [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse ein.  
  
 Kalendersteuerelemente ermöglichen es einem Benutzer, einfach das Datum zu bestimmen und ein anderes Datum auszuwählen.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „Calendar“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Kalendersteuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Kalendersteuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|Kalender<br /><br /> <ul><li>DataGrid<br /><br /> <ul><li>Header (0 oder 1)</li><li>HeaderItem (0 oder 7; die Menge hängt davon ab, wie viele Tage in Spalten angezeigt werden)</li><li>ListItem (die Menge hängt davon ab, wie viele Tage angezeigt werden)</li><li>Button (0 oder 2; für Seitenverwaltung der Kalenderansicht)</li></ul></li></ul>|Kalender<br /><br /> -   ListItem (quantity depends on how many days are displayed)|  
  
 Kalendersteuerelemente können in vielen verschiedenen Formen in der Benutzeroberfläche dargestellt werden. Die einzigen Steuerelemente, die garantiert in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten sind, sind das Datenraster-, Header-, Headerelement- und Listenelement-Steuerelement.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften aufgelistet, deren Wert oder Definition für ein Kalendersteuerelement besonders relevant ist. For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Notizen|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Kalender|Dieser Wert gilt für alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Frameworks.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Kalendersteuerelement ist stets in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Kalendersteuerelement ist stets in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Siehe Hinweise.|Die Bezeichnung des Dokumentsteuerelements. In der Regel wird der Titel des Dokuments verwendet.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Kalender“|Lokalisierte Zeichenfolge für den Steuerelementtyp „Calendar“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Das Kalendersteuerelement erhält seinen Namen in der Regel aus dem aktuellen Datum.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster aufgelistet, die von allen Kalendersteuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster/Mustereigenschaft|Unterstützung|Notizen|  
|---------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Ja|Das Kalendersteuerelement unterstützt immer das Grid-Muster, da die in einem Monat enthaltenen Tage Elemente sind, zwischen denen räumlich navigiert werden kann.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Variabel|Die meisten Kalendersteuerelemente unterstützen seitenbezogenes Kippen der Ansicht. Das Scroll-Muster wird zur Unterstützung der Seitenwechselnavigation empfohlen.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Variabel|Die meisten Kalendersteuerelemente behalten einen bestimmten Tag, einen bestimmten Monat oder ein bestimmtes Jahr als Auswahl des Unterelements. In einigen Kalendersteuerelementen können mehrere Elemente gleichzeitig ausgewählt werden, in anderen jeweils nur ein Element.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Ja|Das Kalendersteuerelement hat immer einen Header in seiner Unterstruktur für die Wochentage, sodass das Table-Muster unterstützt werden muss.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Nein|Das Value-Steuerelementmuster ist für Kalendersteuerelemente nicht notwendig, da der Wert nicht direkt für das Steuerelement festgelegt werden kann. Wenn dem Steuerelement ein bestimmtes Datum zugeordnet ist, müssen die Informationen vom Selection-Steuerelementmuster bereitgestellt werden.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Kalendersteuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung|Notizen|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Scroll-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Scroll-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Scroll-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Scroll-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Scroll-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Scroll-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Erforderlich|Keiner|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.Calendar>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
