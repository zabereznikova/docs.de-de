---
title: 'Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3c8afacfafbe14794bf17a4e9a4df7c175a3668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="41a2b-102">Gewusst wie: Gruppieren, Sortieren und Filtern von Daten in einem DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="41a2b-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="41a2b-103">Es ist häufig hilfreich zum Anzeigen von Daten in einem <xref:System.Windows.Controls.DataGrid> auf unterschiedliche Weise durch Gruppieren, Sortieren und Filtern der Daten.</span><span class="sxs-lookup"><span data-stu-id="41a2b-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="41a2b-104">Zum Gruppieren, Sortieren und Filtern der Daten in einem <xref:System.Windows.Controls.DataGrid>, binden Sie es an eine <xref:System.Windows.Data.CollectionView> , die diese Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="41a2b-105">Anschließend können Sie arbeiten mit den Daten in der <xref:System.Windows.Data.CollectionView> ohne Auswirkung auf den zugrunde liegenden Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="41a2b-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="41a2b-106">Die Änderungen in der Auflistungsansicht werden angezeigt, der <xref:System.Windows.Controls.DataGrid> -Benutzeroberfläche (UI).</span><span class="sxs-lookup"><span data-stu-id="41a2b-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="41a2b-107">Die <xref:System.Windows.Data.CollectionView> Klasse enthält, gruppieren und sortieren die Funktionalität für eine Datenquelle, die implementiert die <xref:System.Collections.IEnumerable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="41a2b-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="41a2b-108">Die <xref:System.Windows.Data.CollectionViewSource> Klasse können Sie zum Festlegen der Eigenschaften von einem <xref:System.Windows.Data.CollectionView> aus XAML.</span><span class="sxs-lookup"><span data-stu-id="41a2b-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="41a2b-109">In diesem Beispiel eine Auflistung von `Task` Objekte gebunden ist, um eine <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="41a2b-110">Die <xref:System.Windows.Data.CollectionViewSource> dient als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="41a2b-111">Gruppieren, Sortieren und Filtern werden ausgeführt, auf die <xref:System.Windows.Data.CollectionViewSource> und angezeigt werden, der <xref:System.Windows.Controls.DataGrid> UI.</span><span class="sxs-lookup"><span data-stu-id="41a2b-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="41a2b-112">![Gruppierte Daten in einem DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="41a2b-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="41a2b-113">Gruppierte Daten in einem DataGrid</span><span class="sxs-lookup"><span data-stu-id="41a2b-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="41a2b-114">Verwenden eine CollectionViewSource als ItemsSource</span><span class="sxs-lookup"><span data-stu-id="41a2b-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="41a2b-115">Zum Gruppieren, Sortieren und Filtern von Daten in eine <xref:System.Windows.Controls.DataGrid> -Steuerelement binden Sie die <xref:System.Windows.Controls.DataGrid> auf eine <xref:System.Windows.Data.CollectionView> , die diese Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="41a2b-116">In diesem Beispiel die <xref:System.Windows.Controls.DataGrid> gebunden ist eine <xref:System.Windows.Data.CollectionViewSource> , die diese Funktionen für bietet eine <xref:System.Collections.Generic.List%601> von `Task` Objekte.</span><span class="sxs-lookup"><span data-stu-id="41a2b-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="41a2b-117">So binden Sie ein DataGrid-Steuerelement an eine CollectionViewSource-Element</span><span class="sxs-lookup"><span data-stu-id="41a2b-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="41a2b-118">Erstellen Sie eine Datensammlung, die implementiert die <xref:System.Collections.IEnumerable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="41a2b-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="41a2b-119">Bei Verwendung von <xref:System.Collections.Generic.List%601> um Ihre Sammlung zu erstellen, erstellen Sie eine neue Klasse, die von erben <xref:System.Collections.Generic.List%601> zu eine Instanz von instanziieren, sondern <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="41a2b-120">Dadurch können Sie zur Datenbindung an die Auflistung in XAML.</span><span class="sxs-lookup"><span data-stu-id="41a2b-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41a2b-121">Die Objekte in der Auflistung implementieren müssen die <xref:System.ComponentModel.INotifyPropertyChanged> geänderte Schnittstelle und die <xref:System.ComponentModel.IEditableObject> Schnittstelle in der Reihenfolge für die <xref:System.Windows.Controls.DataGrid> ordnungsgemäß auf eigenschaftenänderungen und Bearbeitungen reagieren.</span><span class="sxs-lookup"><span data-stu-id="41a2b-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="41a2b-122">Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="41a2b-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="41a2b-123">In XAML, erstellen Sie eine Instanz der Auflistungsklasse, und legen Sie die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="41a2b-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="41a2b-124">In XAML, erstellen Sie eine Instanz von der <xref:System.Windows.Data.CollectionViewSource> Klasse, legen die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md), und legen Sie die Instanz der Auflistungsklasse als die <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="41a2b-125">Erstellen Sie eine Instanz von der <xref:System.Windows.Controls.DataGrid> Klasse, und legen die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft, um die <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="41a2b-126">Für den Zugriff auf die <xref:System.Windows.Data.CollectionViewSource> aus Ihrem Code verwendet die <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> Methode zum Abrufen eines Verweises auf die <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="41a2b-127">Gruppieren von Elementen in einem DataGrid</span><span class="sxs-lookup"><span data-stu-id="41a2b-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="41a2b-128">Um anzugeben, wie Elemente gruppiert sind, in eine <xref:System.Windows.Controls.DataGrid>, verwenden Sie die <xref:System.Windows.Data.PropertyGroupDescription> Typ, um die Elemente in der Datenquellensicht zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="41a2b-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="41a2b-129">Die Gruppierung der Elemente in einem DataGrid mit XAML</span><span class="sxs-lookup"><span data-stu-id="41a2b-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="41a2b-130">Erstellen einer <xref:System.Windows.Data.PropertyGroupDescription> , die Eigenschaft angibt, nach der gruppiert.</span><span class="sxs-lookup"><span data-stu-id="41a2b-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="41a2b-131">Sie können die Eigenschaft in XAML oder in Code angeben.</span><span class="sxs-lookup"><span data-stu-id="41a2b-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="41a2b-132">In XAML Festlegen der <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> auf den Namen der Eigenschaft für die Gruppierung.</span><span class="sxs-lookup"><span data-stu-id="41a2b-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="41a2b-133">Übergeben Sie in Code den Namen der Eigenschaft für die Gruppierung an den Konstruktor übergibt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="41a2b-134">Hinzufügen der <xref:System.Windows.Data.PropertyGroupDescription> auf die <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="41a2b-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="41a2b-135">Fügen Sie zusätzliche Instanzen <xref:System.Windows.Data.PropertyGroupDescription> auf die <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> mehr Gruppierungsebenen hinzuzufügende Auflistung.</span><span class="sxs-lookup"><span data-stu-id="41a2b-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="41a2b-136">Um eine Gruppe zu entfernen, entfernen Sie die <xref:System.Windows.Data.PropertyGroupDescription> aus der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="41a2b-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="41a2b-137">Um alle Gruppen zu entfernen, rufen Sie die <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> Methode der <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="41a2b-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="41a2b-138">Wenn Elemente gruppiert sind, der <xref:System.Windows.Controls.DataGrid>, können Sie definieren eine <xref:System.Windows.Controls.GroupStyle> , die die Darstellung der Gruppe "Jeder" angibt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="41a2b-139">Sie gelten die <xref:System.Windows.Controls.GroupStyle> durch Hinzufügen zu der <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> Auflistung des DataGrid.</span><span class="sxs-lookup"><span data-stu-id="41a2b-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="41a2b-140">Wenn Sie mehrere Gruppierungsebenen verfügen, können Sie verschiedene Formate auf jede Gruppierungsebene anwenden.</span><span class="sxs-lookup"><span data-stu-id="41a2b-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="41a2b-141">Stile werden in der Reihenfolge angewendet, in denen sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="41a2b-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="41a2b-142">Beispielsweise wenn Sie zwei Formate definieren, die erste auf oberste Ebene Zeilengruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="41a2b-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="41a2b-143">Das zweite Format werden für alle Zeilengruppen auf der zweiten Ebene übernommen und niedriger.</span><span class="sxs-lookup"><span data-stu-id="41a2b-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="41a2b-144">Die <xref:System.Windows.FrameworkElement.DataContext%2A> von der <xref:System.Windows.Controls.GroupStyle> ist die <xref:System.Windows.Data.CollectionViewGroup> , die die Gruppe darstellt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="41a2b-145">So ändern Sie die Darstellung von Zeilenköpfen-Gruppe</span><span class="sxs-lookup"><span data-stu-id="41a2b-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="41a2b-146">Erstellen einer <xref:System.Windows.Controls.GroupStyle> , definiert die Darstellung der Zeilengruppe.</span><span class="sxs-lookup"><span data-stu-id="41a2b-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="41a2b-147">Versetzen der <xref:System.Windows.Controls.GroupStyle> innerhalb der `<DataGrid.GroupStyle>` Tags.</span><span class="sxs-lookup"><span data-stu-id="41a2b-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="41a2b-148">Sortieren von Elementen in einem DataGrid</span><span class="sxs-lookup"><span data-stu-id="41a2b-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="41a2b-149">Um anzugeben, wie Elemente sortiert werden, in einer <xref:System.Windows.Controls.DataGrid>, verwenden Sie die <xref:System.ComponentModel.SortDescription> Typ zum Sortieren der Elemente in der Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="41a2b-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="41a2b-150">So sortieren Sie Elemente in einem DataGrid</span><span class="sxs-lookup"><span data-stu-id="41a2b-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="41a2b-151">Erstellen einer <xref:System.ComponentModel.SortDescription> , die Eigenschaft angibt, nach zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="41a2b-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="41a2b-152">Sie können die Eigenschaft in XAML oder in Code angeben.</span><span class="sxs-lookup"><span data-stu-id="41a2b-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="41a2b-153">In XAML Festlegen der <xref:System.ComponentModel.SortDescription.PropertyName%2A> auf den Namen der Eigenschaft, die nach zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="41a2b-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="41a2b-154">Im Code, übergeben Sie den Namen der Eigenschaft, die nach zu sortieren und die <xref:System.ComponentModel.ListSortDirection> an den Konstruktor übergibt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="41a2b-155">Hinzufügen der <xref:System.ComponentModel.SortDescription> auf die <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="41a2b-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="41a2b-156">Fügen Sie zusätzliche Instanzen <xref:System.ComponentModel.SortDescription> auf die <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> -Auflistung, um zusätzliche Eigenschaften sortieren.</span><span class="sxs-lookup"><span data-stu-id="41a2b-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="41a2b-157">Filtern von Elementen in einem DataGrid</span><span class="sxs-lookup"><span data-stu-id="41a2b-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="41a2b-158">Zum Filtern von Elementen in einer <xref:System.Windows.Controls.DataGrid> mithilfe einer <xref:System.Windows.Data.CollectionViewSource>, geben Sie die Filterlogik im Handler für das <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="41a2b-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="41a2b-159">Zum Filtern von Elementen in einem DataGrid</span><span class="sxs-lookup"><span data-stu-id="41a2b-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="41a2b-160">Fügen Sie einen Handler für das <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="41a2b-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="41a2b-161">In der <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignishandler, d. h. die Filterlogik definieren.</span><span class="sxs-lookup"><span data-stu-id="41a2b-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="41a2b-162">Jedes Mal, wenn die Ansicht aktualisiert wird, wird der Filter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="41a2b-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="41a2b-163">Alternativ können Sie Filtern von Elementen in einem <xref:System.Windows.Controls.DataGrid> durch Erstellen einer Methode, die die Filterung Logik und die Einstellung bietet den <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> Eigenschaft, um den Filter anwenden.</span><span class="sxs-lookup"><span data-stu-id="41a2b-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="41a2b-164">Ein Beispiel dieser Methode finden Sie unter [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="41a2b-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41a2b-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41a2b-165">Example</span></span>  
 <span data-ttu-id="41a2b-166">Das folgende Beispiel zeigt, gruppieren, Sortieren und Filtern von `Task` Daten in einem <xref:System.Windows.Data.CollectionViewSource> und Anzeigen der gruppierten, gefiltert und sortiert `Task` Daten in eine <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="41a2b-167">Die <xref:System.Windows.Data.CollectionViewSource> dient als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="41a2b-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="41a2b-168">Gruppieren, Sortieren und Filtern werden ausgeführt, auf die <xref:System.Windows.Data.CollectionViewSource> und angezeigt werden, der <xref:System.Windows.Controls.DataGrid> UI.</span><span class="sxs-lookup"><span data-stu-id="41a2b-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="41a2b-169">Zum Testen dieses Beispiels müssen Sie den Namen "DGGroupSortFilterExample" entsprechend Name Ihres Projekts entsprechend anpassen.</span><span class="sxs-lookup"><span data-stu-id="41a2b-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="41a2b-170">Wenn Sie Visual Basic verwenden, müssen Sie so ändern Sie den Klassennamen für <xref:System.Windows.Window> folgt.</span><span class="sxs-lookup"><span data-stu-id="41a2b-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41a2b-171">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="41a2b-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="41a2b-172">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="41a2b-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="41a2b-173">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41a2b-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a2b-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41a2b-174">See Also</span></span>  
 [<span data-ttu-id="41a2b-175">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="41a2b-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="41a2b-176">Erstellen und Binden an ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="41a2b-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="41a2b-177">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="41a2b-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="41a2b-178">Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="41a2b-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="41a2b-179">Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="41a2b-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
