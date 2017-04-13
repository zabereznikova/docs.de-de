---
title: "Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement | Microsoft Docs"
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
  - "DataGrid [WPF], Filter"
  - "DataGrid [WPF], Gruppe"
  - "DataGrid [WPF], Sortieren"
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement
Es ist oft hilfreich, Daten in einem <xref:System.Windows.Controls.DataGrid> durch Gruppieren, Sortieren und Filtern der Daten auf verschiedene Weise anzuzeigen.  Zum Gruppieren, Sortieren und Filtern der Daten in einem <xref:System.Windows.Controls.DataGrid>, binden Sie es an eine <xref:System.Windows.Data.CollectionView>, die diese Funktionen unterstützt.  Anschließend können Sie mit den Daten in der <xref:System.Windows.Data.CollectionView> arbeiten, ohne die zugrunde liegenden Quelldaten zu beeinflussen.  Die Änderungen in der Auflistungsansicht werden in der <xref:System.Windows.Controls.DataGrid>\-Benutzeroberfläche wiedergegeben.  
  
 Die <xref:System.Windows.Data.CollectionView>\-Klasse stellt Gruppierungs\- und Sortierungsfunktionen für eine Datenquelle bereit, die die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert.  Die <xref:System.Windows.Data.CollectionViewSource>\-Klasse ermöglicht es Ihnen, die Eigenschaften einer <xref:System.Windows.Data.CollectionView> in XAML festzulegen.  
  
 In diesem Beispiel ist eine Auflistung von `Task`\-Objekten an eine <xref:System.Windows.Data.CollectionViewSource> gebunden.  Die <xref:System.Windows.Data.CollectionViewSource> wird als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für das <xref:System.Windows.Controls.DataGrid> verwendet.  Gruppierung, Sortierung und Filterung werden für die <xref:System.Windows.Data.CollectionViewSource> ausgeführt und in der <xref:System.Windows.Controls.DataGrid>\-Benutzeroberfläche angezeigt.  
  
 ![Gruppierte Daten in einem DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF\_DataGridGroups")  
Gruppierte Daten in einem DataGrid  
  
## Verwenden von "CollectionViewSource" als "ItemsSource"  
 Zum Gruppieren, Sortieren und Filtern der Daten in einem <xref:System.Windows.Controls.DataGrid>\-Steuerelement binden Sie das <xref:System.Windows.Controls.DataGrid> an eine <xref:System.Windows.Data.CollectionView>, die diese Funktionen unterstützt.  In diesem Beispiel wird das <xref:System.Windows.Controls.DataGrid> an eine <xref:System.Windows.Data.CollectionViewSource> gebunden, die diese Funktionen für eine <xref:System.Collections.Generic.List%601> mit `Task`\-Objekten bereitstellt.  
  
#### So binden Sie ein DataGrid an eine "CollectionViewSource"  
  
1.  Erstellen Sie eine Datensammlung, die die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert.  
  
     Wenn Sie <xref:System.Collections.Generic.List%601> verwenden, um die Auflistung zu erstellen, sollten Sie eine neue Klasse erstellen, die von <xref:System.Collections.Generic.List%601> erbt, anstatt eine Instanz von <xref:System.Collections.Generic.List%601> zu instanziieren.  Auf diese Weise können Sie in XAML eine Datenbindung an die Auflistung vornehmen.  
  
    > [!NOTE]
    >  Die Objekte in der Auflistung müssen die geänderte <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle und die <xref:System.ComponentModel.IEditableObject>\-Schnittstelle implementieren, damit das <xref:System.Windows.Controls.DataGrid> ordnungsgemäß auf Eigenschaftenänderungen und Bearbeitungen reagiert.  Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  Erstellen Sie in XAML eine Instanz der Auflistungsklasse, und legen Sie die [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) fest.  
  
3.  Erstellen Sie in XAML eine Instanz der <xref:System.Windows.Data.CollectionViewSource>\-Klasse, legen Sie die [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) fest, und legen Sie die Instanz der Auflistungsklasse als <xref:System.Windows.Data.CollectionViewSource.Source%2A> fest.  
  
     [!code-xml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  Erstellen Sie eine Instanz der <xref:System.Windows.Controls.DataGrid>\-Klasse, und legen Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft auf die <xref:System.Windows.Data.CollectionViewSource> fest.  
  
     [!code-xml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  Um im Code auf die <xref:System.Windows.Data.CollectionViewSource> zuzugreifen, rufen Sie mit der <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>\-Methode einen Verweis auf die <xref:System.Windows.Data.CollectionViewSource> ab.  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## Gruppieren von Elementen in einem DataGrid  
 Um anzugeben, wie Elemente in einem <xref:System.Windows.Controls.DataGrid> gruppiert werden, gruppieren Sie die Elemente in der Quellansicht mithilfe des <xref:System.Windows.Data.PropertyGroupDescription>\-Typs.  
  
#### So gruppieren Sie Elemente in ein DataGrid mit XAML  
  
1.  Erstellen Sie eine <xref:System.Windows.Data.PropertyGroupDescription>, die die Eigenschaft angibt, nach der gruppiert werden soll.  Sie können die Eigenschaft in XAML oder im Code festlegen.  
  
    1.  Legen Sie in XAML den <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> auf den Namen der Eigenschaft fest, nach der gruppiert werden soll.  
  
    2.  Übergeben Sie im Code den Namen der Eigenschaft, auf der die Gruppierung basieren soll, an den Konstruktor.  
  
2.  Fügen Sie die <xref:System.Windows.Data.PropertyGroupDescription> der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=fullName>\-Auflistung hinzu.  
  
3.  Fügen Sie der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>\-Auflistung zusätzliche <xref:System.Windows.Data.PropertyGroupDescription>\-Instanzen hinzu, um mehr Gruppierungsebenen hinzuzufügen.  
  
     [!code-xml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  Um eine Gruppe zu entfernen, entfernen Sie die <xref:System.Windows.Data.PropertyGroupDescription> aus der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>\-Auflistung.  
  
5.  Um alle Gruppen zu entfernen, rufen Sie die <xref:System.Collections.ObjectModel.Collection%601.Clear%2A>\-Methode der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>\-Auflistung auf.  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 Wenn Elemente im <xref:System.Windows.Controls.DataGrid> gruppiert werden, können Sie einen <xref:System.Windows.Controls.GroupStyle> definieren, der die Darstellung jeder Gruppe angibt.  Der <xref:System.Windows.Controls.GroupStyle> wird angewendet, indem Sie ihn der <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>\-Auflistung des DataGrid hinzufügen.  Wenn Sie über mehrere Gruppierungsebenen verfügen, können Sie auf die einzelnen Gruppenebenen unterschiedliche Stile anwenden.  Die Stile werden in der Reihenfolge angewendet, in der sie definiert sind.  Wenn Sie z. B. zwei Stile definieren, wird der erste Stil auf die Zeilengruppen der obersten Ebene angewendet.  Der zweite Stil wird auf alle Zeilengruppen der zweiten Ebene und niedriger angewendet.  Der <xref:System.Windows.FrameworkElement.DataContext%2A> des <xref:System.Windows.Controls.GroupStyle> ist die <xref:System.Windows.Data.CollectionViewGroup>, die die Gruppe darstellt.  
  
#### So ändern Sie die Darstellung von Zeilengruppenheadern  
  
1.  Erstellen Sie einen <xref:System.Windows.Controls.GroupStyle>, der die Darstellung der Zeilengruppe definiert.  
  
2.  Platzieren Sie den <xref:System.Windows.Controls.GroupStyle> innerhalb der `<DataGrid.GroupStyle>`\-Tags.  
  
     [!code-xml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## Sortieren von Elementen in einem DataGrid  
 Um anzugeben, wie Elemente in einem <xref:System.Windows.Controls.DataGrid> sortiert werden, sortieren Sie die Elemente in der Quellansicht mithilfe des <xref:System.ComponentModel.SortDescription>\-Typs.  
  
#### So sortieren Sie Elemente in einem DataGrid  
  
1.  Erstellen Sie eine <xref:System.ComponentModel.SortDescription>, die die Eigenschaft angibt, nach der sortiert werden soll.  Sie können die Eigenschaft in XAML oder im Code festlegen.  
  
    1.  Legen Sie in XAML den <xref:System.ComponentModel.SortDescription.PropertyName%2A> auf den Namen der Eigenschaft fest, nach der sortiert werden soll.  
  
    2.  Übergeben Sie im Code den Namen der Eigenschaft, auf dem die Sortierung basieren soll, und die <xref:System.ComponentModel.ListSortDirection> an den Konstruktor.  
  
2.  Fügen Sie die <xref:System.ComponentModel.SortDescription> der <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=fullName>\-Auflistung hinzu.  
  
3.  Fügen Sie der <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A>\-Auflistung zusätzliche Instanzen von <xref:System.ComponentModel.SortDescription> hinzu, um nach zusätzlichen Eigenschaften zu sortieren.  
  
     [!code-xml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## Filtern von Elementen in einem DataGrid  
 Um Elemente in einem <xref:System.Windows.Controls.DataGrid> mithilfe einer <xref:System.Windows.Data.CollectionViewSource> zu filtern, geben Sie die Filterlogik im Handler für das <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=fullName>\-Ereignis an.  
  
#### So filtern Sie Elemente in einem DataGrid  
  
1.  Fügen Sie einen Handler für das <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=fullName>\-Ereignis hinzu.  
  
2.  Definieren Sie im <xref:System.Windows.Data.CollectionViewSource.Filter>\-Handler die Filterlogik.  
  
     Der Filter wird jedes Mal angewendet, wenn die Ansicht aktualisiert wird.  
  
     [!code-xml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 Alternativ können Sie Elemente in einem <xref:System.Windows.Controls.DataGrid> filtern, indem Sie eine Methode erstellen, die die Filterlogik bereitstellt, und die <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=fullName>\-Eigenschaft zum Anwenden des Filters festlegen.  Ein Beispiel für diese Methode finden Sie unter [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
## Beispiel  
 Im folgenden Beispiel werden das Gruppieren, Sortieren und Filtern von `Task`\-Daten in einer <xref:System.Windows.Data.CollectionViewSource> und das Anzeigen der gruppierten, sortierten und gefilterten `Task`\-Daten in einem <xref:System.Windows.Controls.DataGrid> veranschaulicht.  Die <xref:System.Windows.Data.CollectionViewSource> wird als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für das <xref:System.Windows.Controls.DataGrid> verwendet.  Gruppierung, Sortierung und Filterung werden für die <xref:System.Windows.Data.CollectionViewSource> ausgeführt und in der <xref:System.Windows.Controls.DataGrid>\-Benutzeroberfläche angezeigt.  
  
 Um dieses Beispiel zu testen, müssen Sie den Namen "DGGroupSortFilterExample" entsprechend dem Projektnamen anpassen.  Wenn Sie Visual Basic verwenden, müssen Sie den Klassennamen für <xref:System.Windows.Window> wie folgt ändern.  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## Kompilieren des Codes  
  
## Robuste Programmierung  
  
## .NET Framework-Sicherheit  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Erstellen und Binden an ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)   
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)