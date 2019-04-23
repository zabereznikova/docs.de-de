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
ms.openlocfilehash: dda712d58a4ff956de074ecd416402ba0aece5f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197151"
---
# <a name="datagrid"></a>DataGrid
Die <xref:System.Windows.Controls.DataGrid> -Steuerelement können Sie zum Anzeigen und Bearbeiten von Daten aus vielen verschiedenen Quellen, z. B. aus einer SQL-Datenbank, LINQ-Abfrage oder eine beliebige andere bindbare Datenquelle. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../data/binding-sources-overview.md).  
  
 Spalten zeigt Text, Steuerelemente, z. B. eine <xref:System.Windows.Controls.ComboBox>, oder andere WPF-Inhalte, z. B. Bilder, Schaltflächen oder alle Inhalte, die in einer Vorlage enthalten. Sie können eine <xref:System.Windows.Controls.DataGridTemplateColumn> zum Anzeigen von Daten in einer Vorlage definiert. Die folgende Tabelle enthält die Spaltentypen, die standardmäßig bereitgestellt werden.  
  
|Generierte Spaltentyp|Datentyp|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> kann in der Darstellung, wie z. B. Zellenschriftart, Farbe und Größe angepasst werden. <xref:System.Windows.Controls.DataGrid> unterstützt alle Stile und Vorlagen von anderen WPF-Steuerelementen. <xref:System.Windows.Controls.DataGrid> umfasst auch standardmäßig und anpassbare Verhalten für die Bearbeitung, Sortieren und Validierung.  
  
 Die folgende Tabelle enthält einige häufige Aufgaben für <xref:System.Windows.Controls.DataGrid> und wie diese umgesetzt werden können. Anzeigen der zugehörigen API, finden Sie weitere Informationen und Beispielcode.  
  
|Szenario|Ansatz|  
|--------------|--------------|  
|Abwechselnde Hintergrundfarben|Legen Sie die <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> Eigenschaft auf 2 oder mehr, und weisen Sie dann eine <xref:System.Windows.Media.Brush> auf der <xref:System.Windows.Controls.DataGrid.RowBackground%2A> und <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> Eigenschaften.|  
|Definieren von Verhalten der Funktionsauswahl Zell- und Zeilenvorgängen|Legen Sie für die Eigenschaften <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> fest.|  
|Anpassen des Erscheinungsbilds von Headern, Zellen und Zeilen|Wenden Sie ein neues <xref:System.Windows.Style> auf die <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>, oder <xref:System.Windows.Controls.DataGrid.RowStyle%2A> Eigenschaften.|  
|Legen Sie Größenänderungsoptionen|Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, oder <xref:System.Windows.FrameworkElement.MinWidth%2A> Eigenschaften. Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGrid-Steuerelement](sizing-options-in-the-datagrid-control.md).|  
|Zugreifen auf ausgewählte Elemente|Überprüfen Sie die <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> Eigenschaft, um die ausgewählten Zellen abzurufen und die <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> Eigenschaft, um die ausgewählten Zeilen abzurufen. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Anpassen von Endbenutzerinteraktionen|Legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, und <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> Eigenschaften.|  
|Widerrufen oder Ändern von automatisch generierten Spalten|Behandeln der <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> Ereignis.|  
|Fixieren einer Spalte|Legen Sie die <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> -Eigenschaft auf 1 und verschieben Sie die Spalte in der äußersten linken Position durch Festlegen der <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> Eigenschaft auf 0.|  
|Verwenden von XML-Daten als Datenquelle|Binden der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> auf die <xref:System.Windows.Controls.DataGrid> , die XPath-Abfrage, die die Auflistung von Elementen darstellt. Erstellen Sie jede Spalte in der <xref:System.Windows.Controls.DataGrid>. Binden Sie jede Spalte, durch Festlegen der XPath-Ausdruck für die Bindung auf die Abfrage, die Eigenschaft der Quelle des Elements abruft. Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Beschreibt, wie Sie richten Sie ein neues WPF-Projekt ein Entity Framework-Element hinzufügen, legen Sie die Quelle und Anzeigen der Daten in einem <xref:System.Windows.Controls.DataGrid>.|  
|[Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement](how-to-add-row-details-to-a-datagrid-control.md)|Beschreibt das Erstellen von Details für die Zeile für eine <xref:System.Windows.Controls.DataGrid>.|  
|[Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement](how-to-implement-validation-with-the-datagrid-control.md)|Beschreibt das Validieren von Werten in <xref:System.Windows.Controls.DataGrid> Zellen und Zeilen und die Validierungsfeedback anzeigen.|  
|[Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Beschreibt, wie für die Interaktion mit der <xref:System.Windows.Controls.DataGrid> -Steuerelement unter Verwendung der Tastatur und Maus.|  
|[Vorgehensweise: Gruppieren, Sortieren und Filtern von Daten im DataGrid-Steuerelement](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Beschreibt, wie Daten in einem <xref:System.Windows.Controls.DataGrid> auf verschiedene Arten von gruppieren, Sortieren und Filtern der Daten.|  
|[Größenänderungsoptionen im DataGrid-Steuerelement](sizing-options-in-the-datagrid-control.md)|Beschreibt, wie Sie die absolute und automatische größenanpassung in steuern die <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Steuerelemente](index.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
