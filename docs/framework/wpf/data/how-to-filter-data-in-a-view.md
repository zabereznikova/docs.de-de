---
title: 'Gewusst wie: Filtern von Daten in einer Ansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: ea49897ca5e9cb6b639cf7d98ff05bd287c51761
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453486"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="5f2d2-102">Gewusst wie: Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="5f2d2-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="5f2d2-103">In diesem Beispiel wird gezeigt, wie Daten in einer Ansicht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f2d2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f2d2-104">Example</span></span>  
 <span data-ttu-id="5f2d2-105">Zum Erstellen eines Filters definieren Sie eine Methode, die die Filter Logik bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="5f2d2-106">Die-Methode wird als Rückruf verwendet und akzeptiert einen Parameter vom Typ `object`.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="5f2d2-107">Die folgende Methode gibt alle `Order`-Objekte zurück, bei denen die `filled`-Eigenschaft auf "No" festgelegt ist, wobei die restlichen Objekte herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="5f2d2-108">Sie können dann den Filter anwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="5f2d2-109">In diesem Beispiel ist `myCollectionView` ein <xref:System.Windows.Data.ListCollectionView>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="5f2d2-110">Um das Filtern rückgängig zu machen, können Sie die <xref:System.Windows.Data.CollectionView.Filter%2A>-Eigenschaft auf `null`festlegen:</span><span class="sxs-lookup"><span data-stu-id="5f2d2-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="5f2d2-111">Weitere Informationen zum Erstellen oder Abrufen einer Ansicht finden Sie unter Abrufen [der Standardansicht einer Datensammlung](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="5f2d2-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="5f2d2-112">Das komplette Beispiel finden Sie unter [Sortieren und Filtern von Elementen in einem Ansichts](https://go.microsoft.com/fwlink/?LinkID=160040)Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="5f2d2-113">Wenn das View-Objekt aus einem <xref:System.Windows.Data.CollectionViewSource>-Objekt stammt, wenden Sie Filter Logik an, indem Sie einen Ereignishandler für das <xref:System.Windows.Data.CollectionViewSource.Filter>-Ereignis festlegen.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="5f2d2-114">Im folgenden Beispiel ist `listingDataView` eine Instanz von <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="5f2d2-115">Der folgende Code zeigt die Implementierung des Beispiels `ShowOnlyBargainsFilter` Filter Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="5f2d2-116">Dieser Ereignishandler verwendet die <xref:System.Windows.Data.FilterEventArgs.Accepted%2A>-Eigenschaft, um `AuctionItem` Objekte mit einem `CurrentPrice` von $25 oder höher herauszufiltern.</span><span class="sxs-lookup"><span data-stu-id="5f2d2-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5f2d2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f2d2-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="5f2d2-118">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="5f2d2-118">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5f2d2-119">Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="5f2d2-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="5f2d2-120">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="5f2d2-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
