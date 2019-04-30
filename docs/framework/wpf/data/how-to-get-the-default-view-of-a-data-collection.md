---
title: 'Vorgehensweise: Abrufen der Standardansicht einer Datensammlung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 746331e69ee1e5eee795a0e35202f4889b72c53f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931511"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="d68fa-102">Vorgehensweise: Abrufen der Standardansicht einer Datensammlung</span><span class="sxs-lookup"><span data-stu-id="d68fa-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="d68fa-103">Sichten können die Datenerfassung auf unterschiedliche Weise je nach sortieren, filtern oder gruppieren die Kriterien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d68fa-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="d68fa-104">Jede Sammlung verfügt über eine gemeinsame Standardansicht, die als die tatsächliche Bindung-Quelle verwendet wird, wenn eine Bindung eine Sammlung als Quelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="d68fa-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="d68fa-105">In diesem Beispiel veranschaulicht das Abrufen der Standardansicht einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d68fa-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d68fa-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d68fa-106">Example</span></span>  
 <span data-ttu-id="d68fa-107">Um die Ansicht zu erstellen, benötigen Sie einen Objektverweis auf die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="d68fa-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="d68fa-108">Dieses Datenobjekt kann durch Verweisen auf Ihren eigenen Code-Behind-Objekt, durch den Datenkontext, abrufen, indem Abrufen einer Eigenschaft der Datenquelle oder Abrufen einer Eigenschaft der Bindung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d68fa-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="d68fa-109">In diesem Beispiel wird gezeigt, wie zum Abrufen der <xref:System.Windows.FrameworkElement.DataContext%2A> ein Datenobjekt und die Verwendung die standardauflistung direkt abrufen Anzeigeberechtigung für diese Sammlung.</span><span class="sxs-lookup"><span data-stu-id="d68fa-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="d68fa-110">In diesem Beispiel ist das Stammelement ist ein <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="d68fa-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="d68fa-111">Die <xref:System.Windows.FrameworkElement.DataContext%2A> nastaven NA hodnotu *MyDataSource*, die bezieht sich auf einen Datenanbieter, die eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von *Reihenfolge* Objekte.</span><span class="sxs-lookup"><span data-stu-id="d68fa-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="d68fa-112">Alternativ können Sie instanziieren und Binden an eine eigene Auflistung Ansicht mithilfe der <xref:System.Windows.Data.CollectionViewSource> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d68fa-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="d68fa-113">Dieser Auflistungsansicht wird nur von Steuerelementen gemeinsam genutzt, die direkt an ihn binden.</span><span class="sxs-lookup"><span data-stu-id="d68fa-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="d68fa-114">Ein Beispiel finden Sie unter Vorgehensweise erstellen Sie eine Ansicht im Abschnitt der [Übersicht über die Datenbindung](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d68fa-114">For an example, see the How to Create a View section in the [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="d68fa-115">Beispiele für die Funktionalität einer Auflistungsansicht, finden Sie unter [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md), [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md), und [Navigieren durch die Objekte in einer Datenauflistungsansicht](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="d68fa-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68fa-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d68fa-116">See also</span></span>

- [<span data-ttu-id="d68fa-117">Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="d68fa-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="d68fa-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="d68fa-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
