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
ms.openlocfilehash: cdf4bfff8182b62d55f56b823c7ff129de4f9f1c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646120"
---
# <a name="datagrid"></a>DataGrid
Mit <xref:System.Windows.Controls.DataGrid> dem Steuerelement können Sie Daten aus vielen verschiedenen Quellen anzeigen und bearbeiten, z. B. aus einer SQL-Datenbank, einer LINQ-Abfrage oder einer anderen bindbaren Datenquelle. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../data/binding-sources-overview.md).  
  
 Spalten können Text, Steuerelemente, <xref:System.Windows.Controls.ComboBox>z. B. einen , oder andere WPF-Inhalte, z. B. Bilder, Schaltflächen oder alle in einer Vorlage enthaltenen Inhalte anzeigen. Sie können <xref:System.Windows.Controls.DataGridTemplateColumn> eine verwenden, um in einer Vorlage definierte Daten anzuzeigen. In der folgenden Tabelle sind die Spaltentypen aufgeführt, die standardmäßig bereitgestellt werden.  
  
|Generierter Spaltentyp|Datentyp|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>kann in der Darstellung angepasst werden, z. B. Zellschriftart, Farbe und Größe. <xref:System.Windows.Controls.DataGrid>unterstützt alle Styling- und Vorlagenfunktionen anderer WPF-Steuerelemente. <xref:System.Windows.Controls.DataGrid>enthält auch standardmäßige und anpassbare Verhaltensweisen zum Bearbeiten, Sortieren und Überprüfen.  
  
 In der folgenden Tabelle sind <xref:System.Windows.Controls.DataGrid> einige der allgemeinen Aufgaben aufgeführt und wie diese ausgeführt werden können. Wenn Sie die zugehörige API anzeigen, finden Sie weitere Informationen und Beispielcode.  
  
|Szenario|Vorgehensweise|  
|--------------|--------------|  
|Wechselnde Hintergrundfarben|Legen <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> Sie die Eigenschaft auf 2 <xref:System.Windows.Media.Brush> oder <xref:System.Windows.Controls.DataGrid.RowBackground%2A> mehr <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> fest, und weisen Sie dann eine dem und eigenschaften zu.|  
|Definieren des Zell- und Zeilenauswahlverhaltens|Legen Sie die Eigenschaften <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> fest.|  
|Anpassen der visuellen Darstellung von Kopfzeilen, Zellen und Zeilen|Wenden Sie <xref:System.Windows.Style> eine <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>neue <xref:System.Windows.Controls.DataGrid.CellStyle%2A>auf <xref:System.Windows.Controls.DataGrid.RowStyle%2A> die , , oder Eigenschaften an.|  
|Festlegen von Größenoptionen|Legen <xref:System.Windows.FrameworkElement.Height%2A>Sie <xref:System.Windows.FrameworkElement.MaxHeight%2A> <xref:System.Windows.FrameworkElement.MinHeight%2A>die <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A>Eigenschaften <xref:System.Windows.FrameworkElement.MinWidth%2A> , , , , oder fest. Weitere Informationen finden Sie unter [Größenoptionen im DataGrid-Steuerelement](sizing-options-in-the-datagrid-control.md).|  
|Zugriff auf ausgewählte Elemente|Überprüfen <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> Sie die Eigenschaft, um <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> die ausgewählten Zellen und die Eigenschaft abzusuchen, um die ausgewählten Zeilen abzusuchen. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Anpassen von Endbenutzerinteraktionen|Legen <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>Sie <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>Eigenschaften <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> , , , , und fest.|  
|Abbrechen oder Ändern automatisch generierter Spalten|Behandeln <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> Sie das Ereignis.|  
|Einfrieren einer Spalte|Legen <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> Sie die Eigenschaft auf 1 fest, und verschieben <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> Sie die Spalte in die linke Position, indem Sie die Eigenschaft auf 0 setzen.|  
|Verwenden von XML-Daten als Datenquelle|Binden <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Sie <xref:System.Windows.Controls.DataGrid> die an die XPath-Abfrage, die die Auflistung von Elementen darstellt. Erstellen Sie jede <xref:System.Windows.Controls.DataGrid>Spalte im . Binden Sie jede Spalte, indem Sie den XPath für die Bindung an die Abfrage festlegen, die die Eigenschaft für die Elementquelle abruft. Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Beschreibt, wie Sie ein neues WPF-Projekt einrichten, ein Entity Framework-Element <xref:System.Windows.Controls.DataGrid>hinzufügen, die Quelle festlegen und die Daten in einem anzeigen.|  
|[Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement](how-to-add-row-details-to-a-datagrid-control.md)|Beschreibt das Erstellen von <xref:System.Windows.Controls.DataGrid>Zeilendetails für eine .|  
|[Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement](how-to-implement-validation-with-the-datagrid-control.md)|Beschreibt, wie Werte <xref:System.Windows.Controls.DataGrid> in Zellen und Zeilen überprüft und Validierungsfeedback angezeigt wird.|  
|[Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Beschreibt die Interaktion <xref:System.Windows.Controls.DataGrid> mit dem Steuerelement mithilfe von Tastatur und Maus.|  
|[Vorgehensweise: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Beschreibt, wie Daten <xref:System.Windows.Controls.DataGrid> auf unterschiedliche Weise angezeigt werden, indem die Daten gruppiert, sortiert und gefiltert werden.|  
|[Größenänderungsoptionen im DataGrid-Steuerelement](sizing-options-in-the-datagrid-control.md)|Beschreibt, wie die <xref:System.Windows.Controls.DataGrid>absolute und automatische Größenänderung im gesteuert wird.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Steuerelemente](index.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
