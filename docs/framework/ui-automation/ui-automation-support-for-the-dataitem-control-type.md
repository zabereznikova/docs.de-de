---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp
description: Erhalten Sie Informationen zur Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelement. Erlernen Sie die erforderliche Struktur, Eigenschaften, Steuerelement Muster und Ereignisse.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
ms.openlocfilehash: be7e4afcbeb884f63d77fe9aa25342c7f9b49f52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278088"
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den DataItem-Steuerelementtyp

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „DataItem“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Ein Eintrag in einer Kontaktliste ist ein Beispiel für ein Datenelement-Steuerelement. Ein Datenelement-Steuerelement enthält Informationen, die für einen Endbenutzer von Interesse sind. Es ist komplizierter als das einfache Listenelement, da es mehr Informationen enthält.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „DataItem“ erforderlich sind. Die- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Anforderungen gelten für alle Datenelement-Steuerelemente, ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 oder Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  

 In der folgende Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Datenelement-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen über die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Steuerelementansicht|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Inhaltsansicht|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> -Variiert (0 oder mehr; kann in der Hierarchie strukturiert werden)|DataItem<br /><br /> -Variiert (0 oder mehr; kann in der Hierarchie strukturiert werden)|  
  
 Ein DataItem-Element in einem Datenraster kann eine Vielzahl von Objekten hosten, wie etwa eine andere Ebene von Datenelementen oder bestimmte Rasterelemente, z. B. Text, Bilder oder Bearbeitungssteuerelemente. Wenn das DataItem-Element über eine bestimmte Objektrolle verfügt, muss das Element als bestimmter Steuerelementtyp verfügbar gemacht werden, z. B. als ListItem-Steuerelementtyp für ein wählbares Datenelement im Raster.  
  
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  

 Die folgende Tabelle enthält die Eigenschaften, deren Werte oder Definitionen für Datenelement-Steuerelemente besonders relevant sind. Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Eigenschaft|Wert|Notizen|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataItem|Dieser Wert ist für alle Benutzeroberflächen-Frameworks gleich.|  
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
  
|Steuerelementmuster|Support|Notizen|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Depends (Abhängig)|Wenn das Datenelement-Steuerelement erweitert oder reduziert werden kann, um Informationen ein- bzw. auszublenden, muss das ExpandCollapse-Muster unterstützt werden.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Depends (Abhängig)|Datenelemente unterstützen das GridItem-Muster, wenn in einem Container, in dem eine räumliche Navigation von Element zu Element möglich ist, eine Auflistung von Datenelementen verfügbar ist.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Depends (Abhängig)|Alle Datenelemente können mithilfe des ScrollItem-Musters durch einen Bildlauf angezeigt werden, wenn ihr Datencontainer mehr Elemente enthält, als auf den Bildschirm passen.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Ja|Alle Datenelemente müssen das SelectionItem-Muster unterstützen, das anzeigt, ob das Element ausgewählt ist.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Depends (Abhängig)|Wenn das Datenelement in einem DataGrid-Steuerelementtyp enthalten ist, wird dieses Muster unterstützt.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Depends (Abhängig)|Wenn das Datenelement einen Zustand enthält, dessen Werte durchlaufen werden können.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Depends (Abhängig)|Wenn der primäre Text des Datenelements bearbeitbar ist, muss das Value-Muster unterstützt werden.|  
  
## <a name="working-with-data-items-in-large-lists"></a>Arbeiten mit Datenelementen in umfangreichen Listen  

 Bei umfangreichen Listen handelt es sich häufig um Daten, die in [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Frameworks virtualisiert sind, um die Leistung zu verbessern. Aus diesem Grund kann ein Benutzeroberflächenautomatisierungs-Client die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Abfragefeature nicht dazu verwenden, den Inhalt der gesamten Struktur auf die gleiche Weise abzurufen wie den anderer Elementcontainer. Ein Client muss das Element per Bildlauf anzeigen (oder das Steuerelement erweitern, um alle hilfreichen Optionen anzuzeigen), bevor er auf sämtliche Informationen des Datenelements zugreifen kann.  
  
 Wenn `SetFocus` für das- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Element für das Datenelement aufgerufen wird, wird der Microsoft Windows-Explorer-Fall erfolgreich zurückgegeben und bewirkt, dass der Fokus auf den Bearbeitungsvorgang innerhalb der Datenelement-Teilstruktur festgelegt wird.  
  
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  

 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Datenelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Support|Notizen|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depends (Abhängig)|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Keine|  
|Durch geänderte<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Depends (Abhängig)|Keine|  
  
## <a name="dataitem-control-type-example"></a>Beispiel für DataItem-Steuerelementtyp  

 Das folgende Bild zeigt einen DataItem-Steuerelementtyp in einem ListView-Steuerelement mit Unterstützung für detaillierte Informationen für die Spalten.  
  
 ![Grafik eines Listenansichtssteuerelements mit zwei Datenelementen](./media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 Die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, die zum Datenelement gehört, werden unten dargestellt. Die Steuerelementmuster für jedes Automatisierungselement sind in Klammern aufgeführt. Die Gruppe „Contoso“ ist ebenfalls Teil des Rasters des DataGrid-Hoststeuerelements.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Steuerelementansicht|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur – Inhaltsansicht|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|-Group "Configuration Manager" (Tabelle, Raster)<br />-DataItem "Accounts Receivable.doc" (TableItem, GridItem, SelectionItem, aufrufen)<br />-Image "Accounts Receivable.doc"<br />-Edit "Name" (TableItem, GridItem, Value "Accounts Receivable.doc")<br />-Edit "date modified" (TableItem, GridItem, Wert "8/25/2006 3:29 pm")<br />-Edit "size" (GridItem, TableItem, Wert "11,0 KB)<br />-DataItem "Accounts Payable.doc" (TableItem, GridItem, SelectionItem, aufrufen)<br />-   ...|-Group "Configuration Manager" (Tabelle, Raster)<br />-DataItem "Accounts Receivable.doc" (TableItem, GridItem, SelectionItem, aufrufen)<br />-Image "Accounts Receivable.doc"<br />-Edit "Name" (TableItem, GridItem, Value "Accounts Receivable.doc")<br />-Edit "date modified" (TableItem, GridItem, Wert "8/25/2006 3:29 pm")<br />-Edit "size" (GridItem, TableItem, Wert "11,0 KB)<br />-DataItem "Accounts Payable.doc" (TableItem, GridItem, SelectionItem, aufrufen)<br />-   …|  
  
 Wenn ein Raster eine Liste wählbarer Elemente darstellt, können die entsprechenden Benutzeroberflächenelemente mit dem Steuerelementtyp „ListItem“ statt mit dem Steuerelementtyp „DataItem“ verfügbar gemacht werden. Im vorherigen Beispiel können die DataItem-Elemente („Accounts Receivable.doc“ und „Accounts Payable.doc“) unter Group („Contoso“) verbessert werden, wenn Sie diese als ListItem-Steuerelementtypen verfügbar machen, da dieser Typ bereits das Steuerelementmuster „SelectionItem“ unterstützt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.ControlType.DataItem>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
