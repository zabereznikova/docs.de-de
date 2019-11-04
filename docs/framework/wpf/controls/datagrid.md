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
ms.openlocfilehash: f0887f36990de483139a9fde1472a78737cb7b72
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460382"
---
# <a name="datagrid"></a>DataGrid
Das <xref:System.Windows.Controls.DataGrid>-Steuerelement ermöglicht Ihnen das Anzeigen und Bearbeiten von Daten aus vielen verschiedenen Quellen, z. b. aus einer SQL-Datenbank, einer LINQ-Abfrage oder einer anderen bindbaren Datenquelle. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../data/binding-sources-overview.md).  
  
 Spalten können Text, Steuerelemente, wie z. b. eine <xref:System.Windows.Controls.ComboBox>, oder andere WPF-Inhalte, z. b. Bilder, Schaltflächen oder Inhalte, die in einer Vorlage enthalten sind, anzeigen. Sie können eine <xref:System.Windows.Controls.DataGridTemplateColumn> zum Anzeigen von Daten verwenden, die in einer Vorlage definiert sind. In der folgenden Tabelle sind die Spaltentypen aufgeführt, die standardmäßig bereitgestellt werden.  
  
|Generierter Spaltentyp|Datentyp|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> können in Darstellung angepasst werden, wie z. b. Zellen Schriftart, Farbe und Größe. <xref:System.Windows.Controls.DataGrid> unterstützt alle Formatierungs-und Vorlagen Funktionen anderer WPF-Steuerelemente. <xref:System.Windows.Controls.DataGrid> umfasst auch das Standardverhalten und anpassbare Verhalten für die Bearbeitung, Sortierung und Validierung.  
  
 In der folgenden Tabelle werden einige der allgemeinen Aufgaben für <xref:System.Windows.Controls.DataGrid> und deren erreichen aufgeführt. Wenn Sie die zugehörige API anzeigen, finden Sie weitere Informationen und Beispielcode.  
  
|Szenario|Ansatz|  
|--------------|--------------|  
|Abwechselnde Hintergrundfarben|Legen Sie die <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A>-Eigenschaft auf 2 oder mehr fest, und weisen Sie dann den Eigenschaften <xref:System.Windows.Controls.DataGrid.RowBackground%2A> und <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> eine <xref:System.Windows.Media.Brush> zu.|  
|Definieren von Zell-und Zeilenauswahl Verhalten|Legen Sie für die Eigenschaften <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> fest.|  
|Anpassen der visuellen Darstellung von Headern, Zellen und Zeilen|Wenden Sie eine neue <xref:System.Windows.Style> auf die Eigenschaften <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>oder <xref:System.Windows.Controls.DataGrid.RowStyle%2A> an.|  
|Größen Anpassungsoptionen festlegen|Legen Sie die Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>oder <xref:System.Windows.FrameworkElement.MinWidth%2A> fest. Weitere Informationen finden Sie unter [Größen Anpassungsoptionen im DataGrid-Steuer](sizing-options-in-the-datagrid-control.md)Element.|  
|Auf ausgewählte Elemente zugreifen|Überprüfen Sie die <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>-Eigenschaft, um die ausgewählten Zellen und die <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A>-Eigenschaft zum Ermitteln der ausgewählten Zeilen zu erhalten. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Anpassen von Endbenutzer Interaktionen|Legen Sie die Eigenschaften <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>und <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> fest.|  
|Abbrechen oder Ändern von automatisch generierten Spalten|Behandeln Sie das <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>-Ereignis.|  
|Fixieren einer Spalte|Legen Sie die <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A>-Eigenschaft auf 1 fest, und verschieben Sie die Spalte an die linke Position, indem Sie die <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A>-Eigenschaft auf 0 festlegen.|  
|Verwenden von XML-Daten als Datenquelle|Binden Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.DataGrid> an die XPath-Abfrage, die die Auflistung von Elementen darstellt. Erstellen Sie jede Spalte in der <xref:System.Windows.Controls.DataGrid>. Binden Sie jede Spalte, indem Sie den XPath für die Bindung auf die Abfrage festlegen, die die Eigenschaft für die Element Quelle abruft. Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Beschreibt, wie Sie ein neues WPF-Projekt einrichten, ein Entity Framework Element hinzufügen, die Quelle festlegen und die Daten in einem <xref:System.Windows.Controls.DataGrid>anzeigen.|  
|[Gewusst wie: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement](how-to-add-row-details-to-a-datagrid-control.md)|Beschreibt, wie Zeilen Details für eine <xref:System.Windows.Controls.DataGrid>erstellt werden.|  
|[Gewusst wie: Implementieren von Validierung mit dem DataGrid-Steuerelement](how-to-implement-validation-with-the-datagrid-control.md)|Beschreibt das Validieren von Werten in <xref:System.Windows.Controls.DataGrid> Zellen und Zeilen und das Anzeigen des Überprüfungs Feedbacks.|  
|[Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Beschreibt die Interaktion mit dem <xref:System.Windows.Controls.DataGrid>-Steuerelement mithilfe der Tastatur und Maus.|  
|[Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Beschreibt, wie Daten in einer <xref:System.Windows.Controls.DataGrid> auf unterschiedliche Weise angezeigt werden, indem die Daten gruppiert, sortiert und gefiltert werden.|  
|[Größenänderungsoptionen im DataGrid-Steuerelement](sizing-options-in-the-datagrid-control.md)|Beschreibt, wie die absolute und die automatische Größenanpassung im <xref:System.Windows.Controls.DataGrid>gesteuert werden.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Steuerelemente](index.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
