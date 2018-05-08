---
title: 'Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 675c1441201fa1578023d6ed758f389a38f3b79a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement
Es ist häufig hilfreich zum Anzeigen von Daten in einem <xref:System.Windows.Controls.DataGrid> auf unterschiedliche Weise durch Gruppieren, Sortieren und Filtern der Daten. Zum Gruppieren, Sortieren und Filtern der Daten in einem <xref:System.Windows.Controls.DataGrid>, binden Sie es an eine <xref:System.Windows.Data.CollectionView> , die diese Funktionen unterstützt. Anschließend können Sie arbeiten mit den Daten in der <xref:System.Windows.Data.CollectionView> ohne Auswirkung auf den zugrunde liegenden Quelldaten. Die Änderungen in der Auflistungsansicht werden angezeigt, der <xref:System.Windows.Controls.DataGrid> -Benutzeroberfläche (UI).  
  
 Die <xref:System.Windows.Data.CollectionView> Klasse enthält, gruppieren und sortieren die Funktionalität für eine Datenquelle, die implementiert die <xref:System.Collections.IEnumerable> Schnittstelle. Die <xref:System.Windows.Data.CollectionViewSource> Klasse können Sie zum Festlegen der Eigenschaften von einem <xref:System.Windows.Data.CollectionView> aus XAML.  
  
 In diesem Beispiel eine Auflistung von `Task` Objekte gebunden ist, um eine <xref:System.Windows.Data.CollectionViewSource>. Die <xref:System.Windows.Data.CollectionViewSource> dient als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.DataGrid>. Gruppieren, Sortieren und Filtern werden ausgeführt, auf die <xref:System.Windows.Data.CollectionViewSource> und angezeigt werden, der <xref:System.Windows.Controls.DataGrid> UI.  
  
 ![Gruppierte Daten in einem DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")  
Gruppierte Daten in einem DataGrid  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Verwenden eine CollectionViewSource als ItemsSource  
 Zum Gruppieren, Sortieren und Filtern von Daten in eine <xref:System.Windows.Controls.DataGrid> -Steuerelement binden Sie die <xref:System.Windows.Controls.DataGrid> auf eine <xref:System.Windows.Data.CollectionView> , die diese Funktionen unterstützt. In diesem Beispiel die <xref:System.Windows.Controls.DataGrid> gebunden ist eine <xref:System.Windows.Data.CollectionViewSource> , die diese Funktionen für bietet eine <xref:System.Collections.Generic.List%601> von `Task` Objekte.  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>So binden Sie ein DataGrid-Steuerelement an eine CollectionViewSource-Element  
  
1.  Erstellen Sie eine Datensammlung, die implementiert die <xref:System.Collections.IEnumerable> Schnittstelle.  
  
     Bei Verwendung von <xref:System.Collections.Generic.List%601> um Ihre Sammlung zu erstellen, erstellen Sie eine neue Klasse, die von erben <xref:System.Collections.Generic.List%601> zu eine Instanz von instanziieren, sondern <xref:System.Collections.Generic.List%601>. Dadurch können Sie zur Datenbindung an die Auflistung in XAML.  
  
    > [!NOTE]
    >  Die Objekte in der Auflistung implementieren müssen die <xref:System.ComponentModel.INotifyPropertyChanged> geänderte Schnittstelle und die <xref:System.ComponentModel.IEditableObject> Schnittstelle in der Reihenfolge für die <xref:System.Windows.Controls.DataGrid> ordnungsgemäß auf eigenschaftenänderungen und Bearbeitungen reagieren. Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  In XAML, erstellen Sie eine Instanz der Auflistungsklasse, und legen Sie die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md).  
  
3.  In XAML, erstellen Sie eine Instanz von der <xref:System.Windows.Data.CollectionViewSource> Klasse, legen die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md), und legen Sie die Instanz der Auflistungsklasse als die <xref:System.Windows.Data.CollectionViewSource.Source%2A>.  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  Erstellen Sie eine Instanz von der <xref:System.Windows.Controls.DataGrid> Klasse, und legen die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft, um die <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  Für den Zugriff auf die <xref:System.Windows.Data.CollectionViewSource> aus Ihrem Code verwendet die <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> Methode zum Abrufen eines Verweises auf die <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a>Gruppieren von Elementen in einem DataGrid  
 Um anzugeben, wie Elemente gruppiert sind, in eine <xref:System.Windows.Controls.DataGrid>, verwenden Sie die <xref:System.Windows.Data.PropertyGroupDescription> Typ, um die Elemente in der Datenquellensicht zu gruppieren.  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Die Gruppierung der Elemente in einem DataGrid mit XAML  
  
1.  Erstellen einer <xref:System.Windows.Data.PropertyGroupDescription> , die Eigenschaft angibt, nach der gruppiert. Sie können die Eigenschaft in XAML oder in Code angeben.  
  
    1.  In XAML Festlegen der <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> auf den Namen der Eigenschaft für die Gruppierung.  
  
    2.  Übergeben Sie in Code den Namen der Eigenschaft für die Gruppierung an den Konstruktor übergibt.  
  
2.  Hinzufügen der <xref:System.Windows.Data.PropertyGroupDescription> auf die <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> Auflistung.  
  
3.  Fügen Sie zusätzliche Instanzen <xref:System.Windows.Data.PropertyGroupDescription> auf die <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> mehr Gruppierungsebenen hinzuzufügende Auflistung.  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  Um eine Gruppe zu entfernen, entfernen Sie die <xref:System.Windows.Data.PropertyGroupDescription> aus der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> Auflistung.  
  
5.  Um alle Gruppen zu entfernen, rufen Sie die <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> Methode der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> Auflistung.  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 Wenn Elemente gruppiert sind, der <xref:System.Windows.Controls.DataGrid>, können Sie definieren eine <xref:System.Windows.Controls.GroupStyle> , die die Darstellung der Gruppe "Jeder" angibt. Sie gelten die <xref:System.Windows.Controls.GroupStyle> durch Hinzufügen zu der <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> Auflistung des DataGrid. Wenn Sie mehrere Gruppierungsebenen verfügen, können Sie verschiedene Formate auf jede Gruppierungsebene anwenden. Stile werden in der Reihenfolge angewendet, in denen sie definiert sind. Beispielsweise wenn Sie zwei Formate definieren, die erste auf oberste Ebene Zeilengruppen angewendet. Das zweite Format werden für alle Zeilengruppen auf der zweiten Ebene übernommen und niedriger. Die <xref:System.Windows.FrameworkElement.DataContext%2A> von der <xref:System.Windows.Controls.GroupStyle> ist die <xref:System.Windows.Data.CollectionViewGroup> , die die Gruppe darstellt.  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a>So ändern Sie die Darstellung von Zeilenköpfen-Gruppe  
  
1.  Erstellen einer <xref:System.Windows.Controls.GroupStyle> , definiert die Darstellung der Zeilengruppe.  
  
2.  Versetzen der <xref:System.Windows.Controls.GroupStyle> innerhalb der `<DataGrid.GroupStyle>` Tags.  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a>Sortieren von Elementen in einem DataGrid  
 Um anzugeben, wie Elemente sortiert werden, in einer <xref:System.Windows.Controls.DataGrid>, verwenden Sie die <xref:System.ComponentModel.SortDescription> Typ zum Sortieren der Elemente in der Datenquellensicht.  
  
#### <a name="to-sort-items-in-a-datagrid"></a>So sortieren Sie Elemente in einem DataGrid  
  
1.  Erstellen einer <xref:System.ComponentModel.SortDescription> , die Eigenschaft angibt, nach zu sortieren. Sie können die Eigenschaft in XAML oder in Code angeben.  
  
    1.  In XAML Festlegen der <xref:System.ComponentModel.SortDescription.PropertyName%2A> auf den Namen der Eigenschaft, die nach zu sortieren.  
  
    2.  Im Code, übergeben Sie den Namen der Eigenschaft, die nach zu sortieren und die <xref:System.ComponentModel.ListSortDirection> an den Konstruktor übergibt.  
  
2.  Hinzufügen der <xref:System.ComponentModel.SortDescription> auf die <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> Auflistung.  
  
3.  Fügen Sie zusätzliche Instanzen <xref:System.ComponentModel.SortDescription> auf die <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> -Auflistung, um zusätzliche Eigenschaften sortieren.  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a>Filtern von Elementen in einem DataGrid  
 Zum Filtern von Elementen in einer <xref:System.Windows.Controls.DataGrid> mithilfe einer <xref:System.Windows.Data.CollectionViewSource>, geben Sie die Filterlogik im Handler für das <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> Ereignis.  
  
#### <a name="to-filter-items-in-a-datagrid"></a>Zum Filtern von Elementen in einem DataGrid  
  
1.  Fügen Sie einen Handler für das <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> Ereignis.  
  
2.  In der <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignishandler, d. h. die Filterlogik definieren.  
  
     Jedes Mal, wenn die Ansicht aktualisiert wird, wird der Filter angewendet werden.  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 Alternativ können Sie Filtern von Elementen in einem <xref:System.Windows.Controls.DataGrid> durch Erstellen einer Methode, die die Filterung Logik und die Einstellung bietet den <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> Eigenschaft, um den Filter anwenden. Ein Beispiel dieser Methode finden Sie unter [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, gruppieren, Sortieren und Filtern von `Task` Daten in einem <xref:System.Windows.Data.CollectionViewSource> und Anzeigen der gruppierten, gefiltert und sortiert `Task` Daten in eine <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Data.CollectionViewSource> dient als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.DataGrid>. Gruppieren, Sortieren und Filtern werden ausgeführt, auf die <xref:System.Windows.Data.CollectionViewSource> und angezeigt werden, der <xref:System.Windows.Controls.DataGrid> UI.  
  
 Zum Testen dieses Beispiels müssen Sie den Namen "DGGroupSortFilterExample" entsprechend Name Ihres Projekts entsprechend anpassen. Wenn Sie Visual Basic verwenden, müssen Sie so ändern Sie den Klassennamen für <xref:System.Windows.Window> folgt.  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Erstellen und Binden an ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
