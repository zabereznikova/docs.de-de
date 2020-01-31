---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den Bearbeitungssteuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Edit
- Edit control type
- UI Automation, Edit control type
ms.assetid: 6db9d231-c0a0-4e17-910e-ac80357f774f
ms.openlocfilehash: cdbb400d438231689fe35c4bff2bd2946b6bed80
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789506"
---
# <a name="ui-automation-support-for-the-edit-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den Bearbeitungssteuerelementtyp

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).

Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „Edit“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.

Mit einem Bearbeitungssteuerelement kann ein Benutzer eine einfache Textzeile ohne umfangreiche Formatierungsunterstützung anzeigen und bearbeiten

In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „Edit“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Anforderungen gelten für alle Bearbeitungs Steuerelemente, ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 oder Windows Forms.

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur

In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Bearbeitungssteuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen über die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Steuerelementansicht|Inhaltsansicht|
|------------------|------------------|
|Edit|Edit|

Die Steuerelemente, die den Edit-Steuerelementtyp implementieren, enthalten niemals Bildlaufleisten in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, da es sich um ein einzeiliges Steuerelement handelt. Die einzelne Textzeile wird in einigen Layoutszenarien möglicherweise umgebrochen. Der Edit-Steuerelementtyp eignet sich optimal für kleine Mengen von bearbeitbarem oder auswählbarem Text.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für Bearbeitungssteuerelemente besonders relevant sind. Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).

|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|{2&gt;Wert&lt;2}|Hinweise|
|------------------------------------------------------------------------------------|-----------|-----------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Das Bearbeitungssteuerelement muss über einen durch Klicken aktivierbaren Punkt verfügen, der den Eingabefokus an den Bearbeitungsbereich des Steuerelements übergibt, wenn ein Benutzer dort mit der Maus klickt.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Der Name des Bearbeitungssteuerelements wird üblicherweise aus einer statischen Textbezeichnung generiert. Ist keine statische Textbezeichnung vorhanden, muss der Anwendungsentwickler einen Eigenschaftswert für `Name` zuweisen. Die `Name` -Eigenschaft darf niemals den Textinhalt des Bearbeitungssteuerelements enthalten.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Siehe Hinweise.|Wenn dem Steuerelement eine statische Textbezeichnung zugewiesen ist, muss diese Eigenschaft einen Verweis auf dieses Steuerelement verfügbar machen. Ist das Textsteuerelement eine Unterkomponente eines anderen Steuerelements, ist für das Textsteuerelement keine `LabeledBy` -Eigenschaft festgelegt.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Edit|Dieser Wert gilt für alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Frameworks.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Bearbeiten“|Lokalisierte Zeichenfolge für den Steuerelementtyp „Edit“.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Bearbeitungssteuerelement ist stets in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Bearbeitungssteuerelement ist stets in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>|Siehe Hinweise.|Muss für Bearbeitungssteuerelemente auf „true“ festgelegt werden, die Kennwörter enthalten. Wenn ein Bearbeitungssteuerelement Kennwörter enthält, kann diese Eigenschaft von einer Sprachausgabe verwendet werden, um zu ermitteln, ob Tastatureingaben bei der Eingabe durch den Benutzer vorgelesen werden sollen.|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns-and-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster und -Eigenschaften

In der folgenden Tabelle werden die Steuerelementmuster aufgelistet, die von allen Bearbeitungssteuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Steuerelementmuster/Steuerelementmustereigenschaft|Unterstützung/Wert|Hinweise|
|-----------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.Provider.ITextProvider>|Variabel|Bearbeitungssteuerelemente sollten das Text-Steuerelementmuster unterstützen, da ausführliche Textinformationen für Clients immer verfügbar sein sollten.|
|<xref:System.Windows.Automation.Provider.IValueProvider>|Variabel|Alle Bearbeitungssteuerelemente, die eine Zeichenfolge übernehmen, müssen das Value-Muster verfügbar machen.|
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|Siehe Hinweise.|Diese Eigenschaft muss festgelegt werden, um anzugeben, ob für das Steuerelement ein Wert programmgesteuert festgelegt oder er vom Benutzer bearbeitet werden kann.|
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|Siehe Hinweise.|Diese Eigenschaft gibt den Textinhalt des Bearbeitungssteuerelements zurück. Wenn die `IsPasswordProperty` auf `true`festgelegt ist, muss diese Eigenschaft auf Anforderung eine `InvalidOperationException` auslösen.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Variabel|Alle Bearbeitungssteuerelemente, die einen numerischen Bereich übernehmen, müssen das Steuerelementmuster „Range Value“ verfügbar machen.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|Siehe Hinweise.|Diese Eigenschaft muss der kleinste Wert sein, auf den der Inhalt des Bearbeitungssteuerelements festgelegt werden kann.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|Siehe Hinweise.|Diese Eigenschaft muss der größte Wert sein, auf den der Inhalt des Bearbeitungssteuerelements festgelegt werden kann.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|Siehe Hinweise.|Diese Eigenschaft muss die Anzahl der Dezimalstellen angeben, die für den Wert festgelegt werden kann. Wenn das Bearbeitungssteuerelement nur ganze Zahlen annimmt, muss die `SmallChangeProperty` 1 sein. Wenn das Bearbeitungssteuerelement einen Bereich von 1,0 bis 2,0 annimmt, muss die `SmallChangeProperty` 0,1 sein. Wenn das Bearbeitungssteuerelement einen Bereich von 1,00 bis 2,00 annimmt, muss die `SmallChangeProperty` 0,001 sein.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|`Null`|Diese Eigenschaft muss auf einem Bearbeitungssteuerelement nicht verfügbar gemacht werden.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Value%2A>|Siehe Hinweise.|Diese Eigenschaft gibt die numerischen Inhalte des Bearbeitungssteuerelements an. Wenn durch einen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Client innerhalb der Bereiche, die gemäß der Eigenschaften `Minimum` und `Maximum` angegeben sind, ein präziserer Wert festgelegt ist, wird die Value-Eigenschaft automatisch auf den nächsten zulässigen Wert gerundet.|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Bearbeitungssteuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).

|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|-Unterstützung|Hinweise|
|---------------------------------------------------------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Erforderlich|Keine|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Erforderlich|Keine|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|
|Durch geänderte<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keine|
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> -Eigenschaft ausgelöstes Ereignis.|Nie|Keine|
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> -Eigenschaft ausgelöstes Ereignis.|Nie|Keine|
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> -Eigenschaft ausgelöstes Ereignis.|Nie|Keine|
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> -Eigenschaft ausgelöstes Ereignis.|Nie|Keine|
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> -Eigenschaft ausgelöstes Ereignis.|Nie|Keine|
|Durch geänderte<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> -Eigenschaft ausgelöstes Ereignis.|Nie|Keine|
|Durch geänderte<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das „Range Value“-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.Edit>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
