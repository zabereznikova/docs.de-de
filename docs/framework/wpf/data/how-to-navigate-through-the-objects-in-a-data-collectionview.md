---
title: 'Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459705"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="aed8e-102">Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht</span><span class="sxs-lookup"><span data-stu-id="aed8e-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="aed8e-103">Sichten ermöglichen, dass dieselbe Datensammlung in Abhängigkeit von Sortierung, Filterung oder Gruppierung auf verschiedene Weise angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aed8e-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="aed8e-104">Sichten stellen auch ein Aktuelles Datensatz-Zeiger Konzept bereit und ermöglichen das Verschieben des Zeigers.</span><span class="sxs-lookup"><span data-stu-id="aed8e-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="aed8e-105">Dieses Beispiel zeigt, wie das aktuelle-Objekt und die Objekte in einer Datensammlung mithilfe der in der <xref:System.Windows.Data.CollectionView>-Klasse bereitgestellten Funktionalität angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aed8e-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aed8e-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aed8e-106">Example</span></span>  
 <span data-ttu-id="aed8e-107">In diesem Beispiel ist `myCollectionView` ein <xref:System.Windows.Data.CollectionView> Objekt, das eine Ansicht über eine gebundene Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="aed8e-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="aed8e-108">Im folgenden Beispiel ist `OnButton` ein Ereignishandler für die Schaltflächen `Previous` und `Next` in einer Anwendung, die Schaltflächen sind, mit denen der Benutzer in der Datensammlung navigieren kann.</span><span class="sxs-lookup"><span data-stu-id="aed8e-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="aed8e-109">Beachten Sie, dass die Eigenschaften <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> und <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> melden, ob der aktuelle Daten Satz Zeiger am Anfang und am Ende der Liste steht, sodass <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> und <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> entsprechend aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="aed8e-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="aed8e-110">Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A>-Eigenschaft der Sicht wird als `Order` umgewandelt, um das aktuelle Bestell Element in der Auflistung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="aed8e-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="aed8e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aed8e-111">See also</span></span>

- [<span data-ttu-id="aed8e-112">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="aed8e-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="aed8e-113">Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="aed8e-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="aed8e-114">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="aed8e-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="aed8e-115">Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="aed8e-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="aed8e-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="aed8e-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
