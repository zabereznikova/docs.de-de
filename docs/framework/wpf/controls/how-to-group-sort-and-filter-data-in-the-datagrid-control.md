---
title: 'Gewusst wie: Gruppieren, Sortieren und Filtern von Daten im DataGrid-Steuerelement'
description: Erfahren Sie, wie Sie ein Windows Presentation Foundation DataGrid-Steuerelement an eine CollectionView binden, die das Gruppieren, Sortieren und Filtern von Daten in Ansichten unterstützt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 072e5a104a91faa40bb54f2a3fc4ed6188e1112e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167662"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Gewusst wie: Gruppieren, Sortieren und Filtern von Daten im DataGrid-Steuerelement

Es ist oft hilfreich, Daten auf <xref:System.Windows.Controls.DataGrid> unterschiedliche Weise anzuzeigen, indem Sie die Daten gruppieren, Sortieren und filtern. Um die Daten in einer zu gruppieren, zu sortieren und <xref:System.Windows.Controls.DataGrid> zu filtern, binden Sie Sie an einen, der <xref:System.Windows.Data.CollectionView> diese Funktionen unterstützt. Anschließend können Sie mit den Daten in arbeiten, ohne dass sich dies auf <xref:System.Windows.Data.CollectionView> die zugrunde liegenden Quelldaten auswirkt. Die Änderungen in der Sammlungsansicht werden in der <xref:System.Windows.Controls.DataGrid> Benutzeroberfläche angezeigt.

Die <xref:System.Windows.Data.CollectionView> -Klasse stellt Gruppierungs-und Sortierfunktionen für eine Datenquelle bereit, die die- <xref:System.Collections.IEnumerable> Schnittstelle implementiert. Mit der- <xref:System.Windows.Data.CollectionViewSource> Klasse können Sie die Eigenschaften eines <xref:System.Windows.Data.CollectionView> aus XAML festlegen.

In diesem Beispiel ist eine Auflistung von- `Task` Objekten an eine gebunden <xref:System.Windows.Data.CollectionViewSource> . Der <xref:System.Windows.Data.CollectionViewSource> wird als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für das verwendet <xref:System.Windows.Controls.DataGrid> . Gruppieren, Sortieren und Filtern werden auf dem ausgeführt <xref:System.Windows.Data.CollectionViewSource> und in der <xref:System.Windows.Controls.DataGrid> Benutzeroberfläche angezeigt.

![Gruppierte Daten in einem DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Gruppierte Daten in einem DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Verwenden von CollectionViewSource als ItemsSource

Zum Gruppieren, Sortieren und Filtern von Daten in einem- <xref:System.Windows.Controls.DataGrid> Steuerelement binden Sie den <xref:System.Windows.Controls.DataGrid> an einen, der <xref:System.Windows.Data.CollectionView> diese Funktionen unterstützt. In diesem Beispiel ist der <xref:System.Windows.Controls.DataGrid> an einen gebunden, der <xref:System.Windows.Data.CollectionViewSource> diese Funktionen für eine von-Objekten bereitstellt <xref:System.Collections.Generic.List%601> `Task` .

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>So binden Sie ein DataGrid an eine CollectionViewSource

1. Erstellen Sie eine Datensammlung, die die- <xref:System.Collections.IEnumerable> Schnittstelle implementiert.

    Wenn Sie verwenden, <xref:System.Collections.Generic.List%601> um die Auflistung zu erstellen, sollten Sie eine neue Klasse erstellen, die von erbt, <xref:System.Collections.Generic.List%601> anstatt eine Instanz von zu instanziieren <xref:System.Collections.Generic.List%601> . Dies ermöglicht es Ihnen, Daten an die Sammlung in XAML zu binden.

    > [!NOTE]
    > Die-Objekte in der-Auflistung müssen die <xref:System.ComponentModel.INotifyPropertyChanged> geänderte-Schnittstelle und die- <xref:System.ComponentModel.IEditableObject> Schnittstelle implementieren, damit der <xref:System.Windows.Controls.DataGrid> ordnungsgemäß auf Eigenschafts Änderungen und Bearbeitungen antwortet. Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. Erstellen Sie in XAML eine Instanz der Collection-Klasse, und legen Sie die [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md)fest.

3. Erstellen Sie in XAML eine Instanz der- <xref:System.Windows.Data.CollectionViewSource> Klasse, legen Sie die [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md)fest, und legen Sie die Instanz der Auflistungs Klasse als fest <xref:System.Windows.Data.CollectionViewSource.Source%2A> .

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Erstellen Sie eine Instanz der <xref:System.Windows.Controls.DataGrid> -Klasse, und legen <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Sie die-Eigenschaft auf fest <xref:System.Windows.Data.CollectionViewSource> .

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Verwenden Sie die-Methode, um aus dem Code auf das zuzugreifen <xref:System.Windows.Data.CollectionViewSource> , <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> um einen Verweis auf das zu erhalten <xref:System.Windows.Data.CollectionViewSource> .

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Gruppieren von Elementen in einem DataGrid

Um anzugeben, wie Elemente in einer gruppiert werden <xref:System.Windows.Controls.DataGrid> , verwenden Sie den <xref:System.Windows.Data.PropertyGroupDescription> Typ, um die Elemente in der Quell Ansicht zu gruppieren.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>So gruppieren Sie Elemente in einem DataGrid mithilfe von XAML

1. Erstellen <xref:System.Windows.Data.PropertyGroupDescription> Sie einen, der die Eigenschaft angibt, nach der gruppiert werden soll. Sie können die-Eigenschaft in XAML oder im Code angeben.

   1. Legen Sie in XAML den <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> auf den Namen der Eigenschaft fest, nach der gruppiert werden soll.

   2. Übergeben Sie im Code den Namen der Eigenschaft, die von Group by an den Konstruktor übergeben werden soll.

2. Fügen Sie der-Auflistung hinzu <xref:System.Windows.Data.PropertyGroupDescription> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> .

3. Fügen Sie der Sammlung zusätzliche Instanzen von hinzu <xref:System.Windows.Data.PropertyGroupDescription> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> , um weitere Gruppierungs Ebenen hinzuzufügen.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Entfernen Sie das aus der Auflistung, um eine Gruppe zu entfernen <xref:System.Windows.Data.PropertyGroupDescription> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> .

5. Um alle Gruppen zu entfernen, müssen Sie die-Methode der-Auflistung aufzurufen <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> .

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Wenn Elemente in gruppiert werden <xref:System.Windows.Controls.DataGrid> , können Sie einen definieren <xref:System.Windows.Controls.GroupStyle> , der die Darstellung der einzelnen Gruppen angibt. Sie wenden das <xref:System.Windows.Controls.GroupStyle> an, indem Sie es der <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> -Auflistung des DataGrid hinzufügen. Wenn Sie über mehrere Gruppierungs Ebenen verfügen, können Sie für jede Gruppenebene unterschiedliche Stile anwenden. Stile werden in der Reihenfolge angewendet, in der Sie definiert sind. Wenn Sie z. b. zwei Stile definieren, wird die erste auf Zeilen Gruppen auf oberster Ebene angewendet. Der zweite Stil wird auf alle Zeilen Gruppen auf der zweiten Ebene und niedriger angewendet. Der <xref:System.Windows.FrameworkElement.DataContext%2A> des <xref:System.Windows.Controls.GroupStyle> ist der <xref:System.Windows.Data.CollectionViewGroup> , den die Gruppe darstellt.

### <a name="to-change-the-appearance-of-row-group-headers"></a>So ändern Sie die Darstellung von Zeilen Gruppen Headern

1. Erstellen Sie einen <xref:System.Windows.Controls.GroupStyle> , der die Darstellung der Zeilen Gruppe definiert.

2. Fügen Sie die- <xref:System.Windows.Controls.GroupStyle> in die- `<DataGrid.GroupStyle>` Tags ein.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Sortieren von Elementen in einem DataGrid

Um anzugeben, wie Elemente in einer sortiert werden <xref:System.Windows.Controls.DataGrid> , verwenden Sie den- <xref:System.ComponentModel.SortDescription> Typ zum Sortieren der Elemente in der Quell Ansicht.

### <a name="to-sort-items-in-a-datagrid"></a>So sortieren Sie Elemente in einem DataGrid

1. Erstellen <xref:System.ComponentModel.SortDescription> Sie einen, der die Eigenschaft angibt, nach der sortiert werden soll. Sie können die-Eigenschaft in XAML oder im Code angeben.

    1. Legen Sie in XAML den <xref:System.ComponentModel.SortDescription.PropertyName%2A> auf den Namen der Eigenschaft fest, nach der sortiert werden soll.

    2. Übergeben Sie im Code den Namen der Eigenschaft, nach der sortiert werden soll, und die <xref:System.ComponentModel.ListSortDirection> an den Konstruktor.

2. Fügen Sie der-Auflistung hinzu <xref:System.ComponentModel.SortDescription> <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> .

3. Fügen Sie der Sammlung zusätzliche Instanzen von hinzu <xref:System.ComponentModel.SortDescription> <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> , um nach zusätzlichen Eigenschaften zu sortieren.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtern von Elementen in einem DataGrid

Zum Filtern von Elementen in einem <xref:System.Windows.Controls.DataGrid> mithilfe <xref:System.Windows.Data.CollectionViewSource> von Stellen Sie die Filter Logik im-Handler für das- <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> Ereignis bereit.

### <a name="to-filter-items-in-a-datagrid"></a>So filtern Sie Elemente in einem DataGrid-Steuerelement

1. Fügen Sie einen Handler für das- <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> Ereignis hinzu.

2. Definieren Sie im- <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignishandler die Filter Logik.

    Der Filter wird jedes Mal angewendet, wenn die Ansicht aktualisiert wird.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

Alternativ können Sie Elemente in einer filtern, <xref:System.Windows.Controls.DataGrid> indem Sie eine Methode erstellen, die die Filter Logik bereitstellt, und die- <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> Eigenschaft festlegen, um den Filter anzuwenden. Ein Beispiel für diese Methode finden Sie unter [Filtern von Daten in einer Ansicht](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Gruppieren, Sortieren und Filtern von `Task` Daten in einem <xref:System.Windows.Data.CollectionViewSource> und das Anzeigen der gruppierten, sortierten und gefilterten `Task` Daten in einer <xref:System.Windows.Controls.DataGrid> . Der <xref:System.Windows.Data.CollectionViewSource> wird als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für das verwendet <xref:System.Windows.Controls.DataGrid> . Gruppieren, Sortieren und Filtern werden auf dem ausgeführt <xref:System.Windows.Data.CollectionViewSource> und in der <xref:System.Windows.Controls.DataGrid> Benutzeroberfläche angezeigt.

Zum Testen dieses Beispiels müssen Sie den dggroupsortfilterexample-Namen entsprechend Ihrem Projektnamen anpassen. Wenn Sie Visual Basic verwenden, müssen Sie den Klassennamen für <xref:System.Windows.Window> in den folgenden Namen ändern.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Erstellen und Binden an ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtern von Daten in einer Ansicht](../data/how-to-filter-data-in-a-view.md)
- [Sortieren von Daten in einer Ansicht](../data/how-to-sort-data-in-a-view.md)
- [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
