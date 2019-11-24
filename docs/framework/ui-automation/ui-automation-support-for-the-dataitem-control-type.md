---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
ms.openlocfilehash: 9097fdcffb236d08264b881a171a86dcf8801133
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447943"
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „DataItem“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Ein Eintrag in einer Kontaktliste ist ein Beispiel für ein Datenelement-Steuerelement. Ein Datenelement-Steuerelement enthält Informationen, die für einen Endbenutzer von Interesse sind. Es ist komplizierter als das einfache Listenelement, da es mehr Informationen enthält.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „DataItem“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Datenelement-Steuerelemente, egal ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgende Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Datenelement-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen über die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Steuerelementansicht|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Inhaltsansicht|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> -   Varies (0 or more; can be structured in hierarchy)|DataItem<br /><br /> -   Varies (0 or more; can be structured in hierarchy)|  
  
 Ein DataItem-Element in einem Datenraster kann eine Vielzahl von Objekten hosten, wie etwa eine andere Ebene von Datenelementen oder bestimmte Rasterelemente, z. B. Text, Bilder oder Bearbeitungssteuerelemente. Wenn das DataItem-Element über eine bestimmte Objektrolle verfügt, muss das Element als bestimmter Steuerelementtyp verfügbar gemacht werden, z. B. als ListItem-Steuerelementtyp für ein wählbares Datenelement im Raster.  
  
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 Die folgende Tabelle enthält die Eigenschaften, deren Werte oder Definitionen für Datenelement-Steuerelemente besonders relevant sind. Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|property|Wert|Notizen|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataItem|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Datenelement-Steuerelement muss immer ein Inhaltselement sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Datenelement-Steuerelement muss immer ein Steuerelement sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|Siehe Hinweise.|Wenn das Steuerelement einen Status enthält, der dynamisch aktualisiert wird, muss diese Eigenschaft unterstützt werden, damit eine Hilfstechnologie Aktualisierungen empfangen kann, wenn sich der Status des Elements ändert.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|Siehe Hinweise.|Dies ist der Zeichenfolgenwert, der dem Endbenutzer das zugrunde liegende Objekt übermittelt, das vom Element dargestellt wird. Beispiele sind „Mediendatei“ oder „Kontakt“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Datenelement-Steuerelemente verfügen nicht über eine statische Textbezeichnung.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Datenelement“|Lokalisierte Zeichenfolge für den Steuerelementtyp „DataItem“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Das Datenelement-Steuerelement enthält stets ein primäres Textelement, das sich auf den Bezeichner bezieht, den der Benutzer als bedeutungsvollsten Bezeichner mit dem Element assoziieren würde.|  
  
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 Die folgende Tabelle enthält die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementmuster, die von allen DataItem-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster|Unterstützung|Notizen|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Variabel|Wenn das Datenelement-Steuerelement erweitert oder reduziert werden kann, um Informationen ein- bzw. auszublenden, muss das ExpandCollapse-Muster unterstützt werden.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Variabel|Datenelemente unterstützen das GridItem-Muster, wenn in einem Container, in dem eine räumliche Navigation von Element zu Element möglich ist, eine Auflistung von Datenelementen verfügbar ist.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Variabel|Alle Datenelemente können mithilfe des ScrollItem-Musters durch einen Bildlauf angezeigt werden, wenn ihr Datencontainer mehr Elemente enthält, als auf den Bildschirm passen.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Ja|Alle Datenelemente müssen das SelectionItem-Muster unterstützen, das anzeigt, ob das Element ausgewählt ist.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Variabel|Wenn das Datenelement in einem DataGrid-Steuerelementtyp enthalten ist, wird dieses Muster unterstützt.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Variabel|Wenn das Datenelement einen Zustand enthält, dessen Werte durchlaufen werden können.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Variabel|Wenn der primäre Text des Datenelements bearbeitbar ist, muss das Value-Muster unterstützt werden.|  
  
## <a name="working-with-data-items-in-large-lists"></a>Arbeiten mit Datenelementen in umfangreichen Listen  
 Bei umfangreichen Listen handelt es sich häufig um Daten, die in [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Frameworks virtualisiert sind, um die Leistung zu verbessern. Aus diesem Grund kann ein Benutzeroberflächenautomatisierungs-Client die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Abfragefeature nicht dazu verwenden, den Inhalt der gesamten Struktur auf die gleiche Weise abzurufen wie den anderer Elementcontainer. Ein Client muss das Element per Bildlauf anzeigen (oder das Steuerelement erweitern, um alle hilfreichen Optionen anzuzeigen), bevor er auf sämtliche Informationen des Datenelements zugreifen kann.  
  
 When calling `SetFocus` on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element for the data item, the Microsoft Windows Explorer case will return successfully and cause focus to be set to the Edit within the data item subtree.  
  
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Datenelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung|Notizen|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Variabel|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keiner|  
  
## <a name="dataitem-control-type-example"></a>Beispiel für DataItem-Steuerelementtyp  
 Das folgende Bild zeigt einen DataItem-Steuerelementtyp in einem ListView-Steuerelement mit Unterstützung für detaillierte Informationen für die Spalten.  
  
 ![Graphic of a List View control with two data items](./media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 Die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, die zum Datenelement gehört, werden unten dargestellt. Die Steuerelementmuster für jedes Automatisierungselement sind in Klammern aufgeführt. Die Gruppe „Contoso“ ist ebenfalls Teil des Rasters des DataGrid-Hoststeuerelements.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Steuerelementansicht|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Inhaltsansicht|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|-   Group "Contoso" (Table, Grid)<br />-   DataItem "Accounts Receivable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   Image "Accounts Receivable.doc"<br />-   Edit "Name" (TableItem, GridItem, Value "Accounts Receivable.doc")<br />-   Edit "Date modified" (TableItem, GridItem, Value "8/25/2006 3:29 PM")<br />-   Edit "Size" (GridItem, TableItem, Value "11.0 KB)<br />-   DataItem "Accounts Payable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   ...|-   Group "Contoso" (Table, Grid)<br />-   DataItem "Accounts Receivable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   Image "Accounts Receivable.doc"<br />-   Edit "Name" (TableItem, GridItem, Value "Accounts Receivable.doc")<br />-   Edit "Date modified" (TableItem, GridItem, Value "8/25/2006 3:29 PM")<br />-   Edit "Size" (GridItem, TableItem, Value "11.0 KB)<br />-   DataItem "Accounts Payable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   …|  
  
 Wenn ein Raster eine Liste wählbarer Elemente darstellt, können die entsprechenden Benutzeroberflächenelemente mit dem Steuerelementtyp „ListItem“ statt mit dem Steuerelementtyp „DataItem“ verfügbar gemacht werden. Im vorherigen Beispiel können die DataItem-Elemente („Accounts Receivable.doc“ und „Accounts Payable.doc“) unter Group („Contoso“) verbessert werden, wenn Sie diese als ListItem-Steuerelementtypen verfügbar machen, da dieser Typ bereits das Steuerelementmuster „SelectionItem“ unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.DataItem>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
