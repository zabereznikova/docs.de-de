---
title: "DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente [WPF], DataGrid"
  - "DataGrid [WPF], Allgemeine Aufgaben für"
  - "DataGrid [WPF], Anpassen der Darstellung von"
  - "DataGrid-Spaltentypen [WPF]"
  - "DataGrid-Spalten [WPF], Verwenden"
  - "DataGrid-Steuerelement [WPF]"
  - "DataGrid-Szenarios [WPF]"
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DataGrid
Das <xref:System.Windows.Controls.DataGrid>\-Steuerelement ermöglicht Ihnen, Daten aus zahlreichen verschiedenen Quellen, z. B. aus einer SQL\-Datenbank, einer LINQ\-Abfrage oder einer anderen bindungsfähigen Datenquelle, anzuzeigen und zu bearbeiten.  Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Spalten können Text, Steuerelemente, z. B. ein <xref:System.Windows.Controls.ComboBox> oder beliebigen anderen WPF\-Inhalt anzeigen, z. B. Bilder, Schaltflächen oder beliebiger Inhalt, der in einer Vorlage enthalten ist.  Sie können in einer Vorlage definierte Daten mithilfe eines <xref:System.Windows.Controls.DataGridTemplateColumn> anzeigen.  In der folgenden Tabelle sind die standardmäßig bereitgestellten Spaltentypen aufgeführt.  
  
|Generierter Spaltentyp|Datentyp|  
|----------------------------|--------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> kann in der Darstellung, z. B. Zellenschriftart, Farbe und Größe, angepasst werden.  <xref:System.Windows.Controls.DataGrid> unterstützt alle Format\- und Vorlagenfunktionen anderer WPF\-Steuerelemente.  <xref:System.Windows.Controls.DataGrid> schließt auch Standard und vom Benutzer anpassbares Verhalten für Bearbeitung, Sortierung und Validierung ein.  
  
 In der folgenden Tabelle sind einige der gängigen Aufgaben für <xref:System.Windows.Controls.DataGrid> und deren Ausführung aufgeführt.  Durch Anzeigen der zugehörigen API erhalten Sie ggf. weitere Informationen und Beispielcode.  
  
|Szenario|Vorgehensweise|  
|--------------|--------------------|  
|Abwechseln von Hintergrundfarben|Legen Sie die <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A>\-Eigenschaft auf 2 oder mehr fest, und weisen sie den <xref:System.Windows.Controls.DataGrid.RowBackground%2A>\- und <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A>\-Eigenschaften ein <xref:System.Windows.Media.Brush>\-Element zu.|  
|Definieren des Zellen\- und Zeilenauswahlverhaltens|Legen Sie die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>\- und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>\-Eigenschaften fest.|  
|Anpassen des Erscheinungsbilds von Headern, Zellen und Zeilen|Wenden Sie ein neues <xref:System.Windows.Style>\-Element auf die <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>\-, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>\-, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>\- oder <xref:System.Windows.Controls.DataGrid.RowStyle%2A>\-Eigenschaften an.|  
|Festlegen von Größenänderungsoptionen|Legen Sie die Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> oder <xref:System.Windows.FrameworkElement.MinWidth%2A> fest.  Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md).|  
|Zugreifen auf ausgewählte Elemente|Überprüfen Sie die <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>\-Eigenschaft, um die ausgewählten Zellen abzurufen, und die <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A>\-Eigenschaft, um die ausgewählten Zeilen abzurufen.  Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Anpassen von Endbenutzerinteraktionen|Legen Sie die Eigenschaften <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> und <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> fest.|  
|Abbrechen oder Ändern von automatisch generierten Spalten|Behandeln des <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>\-Ereignisses.|  
|Fixieren einer Spalte|Legen Sie die <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A>\-Eigenschaft auf 1 fest, und verschieben Sie die Spalte an die äußerste linke Position, in dem Sie die <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A>\-Eigenschaft auf 0 festlegen.|  
|Verwenden von XML\-Daten als Datenquelle|Binden Sie das <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Element auf dem <xref:System.Windows.Controls.DataGrid> an die XPath\-Abfrage, die die Auflistung von Elementen darstellt.  Erstellen Sie jede Spalte im <xref:System.Windows.Controls.DataGrid>.  Binden Sie jede Spalte, indem Sie den XPath für die Bindung an die Abfrage festlegen, von der die Eigenschaft für die Elementquelle abgerufen wird.  Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server\-Datenbank in einem DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Hier wird beschrieben, wie Sie ein neues WPF\-Projekt einrichten, ein Entity Framework Element hinzufügen, die Quelle festlegen und die Daten in einem <xref:System.Windows.Controls.DataGrid> anzeigen.|  
|[Gewusst wie: Hinzufügen von Zeilendetails zu einem DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|Hier wird beschrieben, wie Sie Zeilendetails für ein <xref:System.Windows.Controls.DataGrid> erstellen.|  
|[Gewusst wie: Implementieren von Validierung mit dem DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|Hier wird beschrieben, wie Sie Werte in <xref:System.Windows.Controls.DataGrid>\-Zellen und \-Zeilen überprüfen und Validierungsfeedback anzeigen.|  
|[Standardverhalten von Tastatur und Maus im DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Hier wird beschrieben, wie Sie über die Tastatur und Maus mit dem <xref:System.Windows.Controls.DataGrid>\-Steuerelement interagieren.|  
|[Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Hier wird beschrieben, wie Sie Daten in einem <xref:System.Windows.Controls.DataGrid> durch Gruppieren, Sortieren und Filtern auf unterschiedliche Weise anzeigen.|  
|[Größenänderungsoptionen im DataGrid\-Steuerelement](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|Beschreibt, wie die absolute und automatische Größenanpassung im <xref:System.Windows.Controls.DataGrid> gesteuert wird.|  
  
## Siehe auch  
 <xref:System.Windows.Controls.DataGrid>   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)   
 [WPF\-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md)