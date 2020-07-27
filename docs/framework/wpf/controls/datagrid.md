---
title: DataGrid
description: Erfahren Sie, wie Sie mit dem DataGrid-Steuerelement Daten aus unterschiedlichen Quellen anzeigen und bearbeiten können, z. b. eine Datenbank, eine LINQ-Abfrage oder eine beliebige andere bindbare Datenquelle.
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
ms.openlocfilehash: 3db49c12fcb363ef7f99e5c69beae09ab05addcf
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168316"
---
# <a name="datagrid"></a>DataGrid
Das <xref:System.Windows.Controls.DataGrid> -Steuerelement ermöglicht Ihnen das Anzeigen und Bearbeiten von Daten aus vielen verschiedenen Quellen, z. b. aus einer SQL-Datenbank, einer LINQ-Abfrage oder einer anderen bindbaren Datenquelle. Weitere Informationen finden Sie unter [Übersicht über Bindungs Quellen](../data/binding-sources-overview.md).  
  
 Spalten können Text, Steuerelemente, wie z. b. <xref:System.Windows.Controls.ComboBox> oder andere WPF-Inhalte, z. b. Bilder, Schaltflächen oder Inhalte, die in einer Vorlage enthalten sind, anzeigen. Sie können einen <xref:System.Windows.Controls.DataGridTemplateColumn> zum Anzeigen von Daten verwenden, die in einer Vorlage definiert sind. In der folgenden Tabelle sind die Spaltentypen aufgeführt, die standardmäßig bereitgestellt werden.  
  
|Generierter Spaltentyp|Datentyp|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>kann in Darstellung angepasst werden, wie z. b. Zellen Schriftart, Farbe und Größe. <xref:System.Windows.Controls.DataGrid>unterstützt alle Formatierungs-und Vorlagen Funktionen anderer WPF-Steuerelemente. <xref:System.Windows.Controls.DataGrid>umfasst auch standardmäßige und anpassbare Verhalten für die Bearbeitung, Sortierung und Validierung.  
  
 In der folgenden Tabelle sind einige der allgemeinen Aufgaben für <xref:System.Windows.Controls.DataGrid> und deren Erreichung aufgeführt. Wenn Sie die zugehörige API anzeigen, finden Sie weitere Informationen und Beispielcode.  
  
|Szenario|Ansatz|  
|--------------|--------------|  
|Abwechselnde Hintergrundfarben|Legen <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> Sie die-Eigenschaft auf zwei oder mehr fest, und weisen <xref:System.Windows.Media.Brush> Sie dann der-Eigenschaft und der-Eigenschaft zu <xref:System.Windows.Controls.DataGrid.RowBackground%2A> <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> .|  
|Definieren von Zell-und Zeilenauswahl Verhalten|Legen Sie die Eigenschaften <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> fest.|  
|Anpassen der visuellen Darstellung von Headern, Zellen und Zeilen|Wenden Sie eine neue <xref:System.Windows.Style> auf <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A> die <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A> Eigenschaften,, <xref:System.Windows.Controls.DataGrid.CellStyle%2A> oder an <xref:System.Windows.Controls.DataGrid.RowStyle%2A> .|  
|Größen Anpassungsoptionen festlegen|Legen Sie <xref:System.Windows.FrameworkElement.Height%2A> die <xref:System.Windows.FrameworkElement.MaxHeight%2A> Eigenschaften,,, <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.Width%2A> , <xref:System.Windows.FrameworkElement.MaxWidth%2A> oder fest <xref:System.Windows.FrameworkElement.MinWidth%2A> . Weitere Informationen finden Sie unter [Größen Anpassungsoptionen im DataGrid-Steuer](sizing-options-in-the-datagrid-control.md)Element.|  
|Auf ausgewählte Elemente zugreifen|Überprüfen Sie die <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> -Eigenschaft, um die ausgewählten Zellen und die- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> Eigenschaft zum Ermitteln der ausgewählten Zeilen zu erhalten. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Anpassen von Endbenutzer Interaktionen|Legen Sie <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A> die <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A> Eigenschaften,,, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> , <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> und fest <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> .|  
|Abbrechen oder Ändern von automatisch generierten Spalten|Behandeln Sie das- <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> Ereignis.|  
|Fixieren einer Spalte|Legen <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> Sie die-Eigenschaft auf 1 fest, und verschieben Sie die Spalte an die linke Position, indem Sie die- <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> Eigenschaft auf 0 festlegen.|  
|Verwenden von XML-Daten als Datenquelle|Binden <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Sie die für das <xref:System.Windows.Controls.DataGrid> an die XPath-Abfrage, die die Auflistung von Elementen darstellt. Erstellen Sie jede Spalte in der <xref:System.Windows.Controls.DataGrid> . Binden Sie jede Spalte, indem Sie den XPath für die Bindung auf die Abfrage festlegen, die die Eigenschaft für die Element Quelle abruft. Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|BESCHREIBUNG|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Beschreibt, wie Sie ein neues WPF-Projekt einrichten, ein Entity Framework Element hinzufügen, die Quelle festlegen und die Daten in einem anzeigen <xref:System.Windows.Controls.DataGrid> .|  
|[Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement](how-to-add-row-details-to-a-datagrid-control.md)|Beschreibt, wie Zeilen Details für ein erstellt werden <xref:System.Windows.Controls.DataGrid> .|  
|[Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement](how-to-implement-validation-with-the-datagrid-control.md)|Beschreibt das Validieren von Werten in <xref:System.Windows.Controls.DataGrid> Zellen und Zeilen und das Anzeigen des Überprüfungs Feedbacks.|  
|[Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Beschreibt die Interaktion mit dem- <xref:System.Windows.Controls.DataGrid> Steuerelement mithilfe der Tastatur und Maus.|  
|[Vorgehensweise: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Beschreibt, wie Daten in einer auf <xref:System.Windows.Controls.DataGrid> unterschiedliche Weise angezeigt werden, indem die Daten gruppiert, sortiert und gefiltert werden.|  
|[Größenänderungsoptionen im DataGrid-Steuerelement](sizing-options-in-the-datagrid-control.md)|Beschreibt, wie die absolute und die automatische Größenanpassung in der gesteuert werden <xref:System.Windows.Controls.DataGrid> .|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.DataGrid>
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Steuerelemente](index.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
