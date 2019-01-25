---
title: 'Vorgehensweise: Filtern von Daten in einer Ansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: 33af517c086f8f89cc06a1de7a2979c5b1624109
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689321"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="16c7a-102">Vorgehensweise: Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="16c7a-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="16c7a-103">Dieses Beispiel zeigt, wie Sie Daten in einer Ansicht zu filtern.</span><span class="sxs-lookup"><span data-stu-id="16c7a-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16c7a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16c7a-104">Example</span></span>  
 <span data-ttu-id="16c7a-105">Um einen Filter zu erstellen, definieren Sie eine Methode, die Filterlogik bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="16c7a-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="16c7a-106">Die Methode, die als Rückruf verwendet wird, und akzeptiert einen Parameter vom Typ `object`.</span><span class="sxs-lookup"><span data-stu-id="16c7a-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="16c7a-107">Die folgende Methode gibt alle der `Order` Objekte mit der `filled` -Eigenschaft auf "Nein" können die restlichen Objekte filtern.</span><span class="sxs-lookup"><span data-stu-id="16c7a-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="16c7a-108">Sie können dann den Filter anwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="16c7a-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="16c7a-109">In diesem Beispiel `myCollectionView` ist eine <xref:System.Windows.Data.ListCollectionView> Objekt.</span><span class="sxs-lookup"><span data-stu-id="16c7a-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="16c7a-110">Um die Filterung rückgängig zu machen, Sie können festlegen, die <xref:System.Windows.Data.CollectionView.Filter%2A> Eigenschaft `null`:</span><span class="sxs-lookup"><span data-stu-id="16c7a-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="16c7a-111">Weitere Informationen zum Erstellen oder eine Ansicht zu erhalten, finden Sie unter [Abrufen der Standardansicht einer datenauflistung](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="16c7a-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="16c7a-112">Das vollständige Beispiel finden Sie unter [sortieren und Filtern von Elementen in einem Beispiel für die Ansicht](https://go.microsoft.com/fwlink/?LinkID=160040).</span><span class="sxs-lookup"><span data-stu-id="16c7a-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="16c7a-113">Wenn Ihr Objekt stammt eine <xref:System.Windows.Data.CollectionViewSource> -Objekts können Sie Filterlogik anwenden, indem Sie einen Ereignishandler für das Festlegen der <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="16c7a-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="16c7a-114">Im folgenden Beispiel `listingDataView` ist eine Instanz der <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="16c7a-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="16c7a-115">Das folgende Beispiel zeigt die Implementierung des Beispiels `ShowOnlyBargainsFilter` Filter-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="16c7a-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="16c7a-116">Dieser Ereignishandler verwendet die <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> Eigenschaft filtern, die `AuctionItem` Objekte mit einer `CurrentPrice` von 25 $ oder höher.</span><span class="sxs-lookup"><span data-stu-id="16c7a-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="16c7a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c7a-117">See also</span></span>
- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="16c7a-118">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="16c7a-118">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="16c7a-119">Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="16c7a-119">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="16c7a-120">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="16c7a-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
