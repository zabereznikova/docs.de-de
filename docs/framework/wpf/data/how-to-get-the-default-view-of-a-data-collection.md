---
title: 'Gewusst wie: Abrufen der Standardansicht einer Datenauflistung'
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
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="88c9b-102">Gewusst wie: Abrufen der Standardansicht einer Datenauflistung</span><span class="sxs-lookup"><span data-stu-id="88c9b-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="88c9b-103">Ansichten können die gleichen Datensammlung unterschiedlich, je nach sortieren, filtern oder Gruppierungskriterien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="88c9b-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="88c9b-104">Jede Auflistung verfügt über eine freigegebene Standardansicht, die als tatsächliche Bindungsquelle verwendet wird, wenn eine Bindung eine Auflistung als Updatequelle angibt.</span><span class="sxs-lookup"><span data-stu-id="88c9b-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="88c9b-105">In diesem Beispiel wird gezeigt, wie die Standardansicht einer Auflistung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="88c9b-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88c9b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88c9b-106">Example</span></span>  
 <span data-ttu-id="88c9b-107">Um die Ansicht zu erstellen, benötigen Sie einen Objektverweis auf die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="88c9b-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="88c9b-108">Dieses Datenobjekt kann durch Verweisen auf Ihren eigenen Code-Behind-Objekt, durch den Datenkontext abrufen, indem Abrufen einer Eigenschaft der Datenquelle oder Abrufen einer Eigenschaft der Bindung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="88c9b-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="88c9b-109">In diesem Beispiel wird gezeigt, wie zum Abrufen der <xref:System.Windows.FrameworkElement.DataContext%2A> des ein Datenobjekt und verwenden Sie ihn direkt der standardauflistung abgerufen für diese Sammlung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88c9b-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="88c9b-110">In diesem Beispiel ist das Stammelement einer <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="88c9b-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="88c9b-111">Die <xref:System.Windows.FrameworkElement.DataContext%2A> auf festgelegt ist *MyDataSource*, dem bezieht sich auf einen Datenanbieter, der eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von *Reihenfolge* Objekte.</span><span class="sxs-lookup"><span data-stu-id="88c9b-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="88c9b-112">Alternativ können Sie instanziieren und Binden an Ihre eigene Auflistung Ansicht mithilfe der <xref:System.Windows.Data.CollectionViewSource> Klasse.</span><span class="sxs-lookup"><span data-stu-id="88c9b-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="88c9b-113">Dieser Auflistungsansicht wird nur von Steuerelementen gemeinsam genutzt, die direkt an diese binden.</span><span class="sxs-lookup"><span data-stu-id="88c9b-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="88c9b-114">Ein Beispiel finden Sie in den zum Erstellen eine Ansicht im Abschnitt der [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="88c9b-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="88c9b-115">Beispiele für die Funktionalität, die von einer Auflistungsansicht bereitgestellt, finden Sie unter [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), und [navigieren Sie über die Objekte in einer Datenauflistungsansicht](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="88c9b-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c9b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88c9b-116">See Also</span></span>  
 [<span data-ttu-id="88c9b-117">Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="88c9b-117">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="88c9b-118">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="88c9b-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
