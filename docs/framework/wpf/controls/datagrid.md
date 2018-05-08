---
title: DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: a8f267706c1ace02b091329360779711981d01e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="datagrid"></a>DataGrid
Die <xref:System.Windows.Controls.DataGrid> Steuerelement können Sie anzeigen und Bearbeiten von Daten aus vielen verschiedenen Quellen, wie z. B. von einer SQL-Datenbank, die LINQ-Abfrage oder eine beliebige andere bindbare Datenquelle. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Spalten können Text, Steuerelemente, anzeigen, wie z. B. eine <xref:System.Windows.Controls.ComboBox>, oder anderen WPF-Inhalt, z. B. Bilder, Schaltflächen oder alle Inhalte, die in einer Vorlage enthalten. Sie können eine <xref:System.Windows.Controls.DataGridTemplateColumn> zum Anzeigen von Datentyps in einer Vorlage definiert. Die folgende Tabelle enthält die Spaltentypen, die standardmäßig bereitgestellt werden.  
  
|Generierte Spaltentyp|Datentyp|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> kann in der Darstellung, z. B. Zellenschriftart, Farbe und Größe angepasst werden. <xref:System.Windows.Controls.DataGrid> unterstützt alle Erstellen von Formaten und Vorlagen von anderen WPF-Steuerelementen. <xref:System.Windows.Controls.DataGrid> enthält auch, Standard und anpassbare Verhalten für die Bearbeitung, Sortierung und Validierung.  
  
 Die folgende Tabelle enthält einige der allgemeinen Aufgaben für <xref:System.Windows.Controls.DataGrid> und erläutert, wie sie ausgeführt. Durch Anzeigen der zugehörigen API, finden Sie weitere Informationen und Beispielcode.  
  
|Szenario|Ansatz|  
|--------------|--------------|  
|Abwechselnde Hintergrundfarben|Festlegen der <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> -Eigenschaft auf 2 oder mehr, und weisen Sie ihm eine <xref:System.Windows.Media.Brush> auf die <xref:System.Windows.Controls.DataGrid.RowBackground%2A> und <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> Eigenschaften.|  
|Definieren von Zellen- und Auswahlverhalten|Legen Sie für die Eigenschaften <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> fest.|  
|Anpassen des Erscheinungsbilds von Headern, Zellen und Zeilen|Wenden Sie ein neues <xref:System.Windows.Style> auf die <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>, oder <xref:System.Windows.Controls.DataGrid.RowStyle%2A> Eigenschaften.|  
|Festlegen von Größenänderungsoptionen|Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, oder <xref:System.Windows.FrameworkElement.MinWidth%2A> Eigenschaften. Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md).|  
|Zugreifen auf ausgewählte Elemente|Überprüfen Sie die <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> Eigenschaft, um die ausgewählten Zellen abzurufen und die <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> Eigenschaft, um die ausgewählten Zeilen abzurufen. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Anpassen von Endbenutzerinteraktionen|Legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, und <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> Eigenschaften.|  
|"Abbrechen", oder Ändern von automatisch generierten Spalten|Behandeln der <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> Ereignis.|  
|Fixieren einer Spalte|Legen Sie die <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> -Eigenschaft auf 1 und verschieben Sie die Spalte in die linke Position durch Festlegen der <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> Eigenschaft auf 0.|  
|Verwenden von XML-Daten als Datenquelle|Binden der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> auf die <xref:System.Windows.Controls.DataGrid> der XPath-Abfrage, die die Auflistung von Elementen darstellt. Erstellen Sie jede Spalte in der <xref:System.Windows.Controls.DataGrid>. Binden Sie jede Spalte, durch Festlegen der XPath-Ausdruck für die Bindung an die Abfrage, die auf die Quelle für die Eigenschaft abruft. Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Beschreibt, wie Sie richten ein neues WPF-Projekt ein Entity Framework-Element hinzufügen, legen Sie die Quelle und Anzeigen der Daten in einem <xref:System.Windows.Controls.DataGrid>.|  
|[Gewusst wie: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|Enthält Informationen zum Erstellen von Zeilendetails für eine <xref:System.Windows.Controls.DataGrid>.|  
|[Gewusst wie: Implementieren von Validierung mit dem DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|Beschreibt, wie zum Überprüfen der Werte in <xref:System.Windows.Controls.DataGrid> -Zellen und Zeilen und Anzeige Überprüfung Feedback.|  
|[Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Beschreibt die Interaktion mit der <xref:System.Windows.Controls.DataGrid> -Steuerelement mithilfe der Tastatur und Maus.|  
|[Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Beschreibt das Anzeigen von Daten in einem <xref:System.Windows.Controls.DataGrid> auf unterschiedliche Weise durch Gruppieren, Sortieren und Filtern der Daten.|  
|[Größenänderungsoptionen im DataGrid-Steuerelement](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|Beschreibt, wie für absolute als auch automatische größenanpassung in steuern die <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.DataGrid>  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
 [WPF-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md)
