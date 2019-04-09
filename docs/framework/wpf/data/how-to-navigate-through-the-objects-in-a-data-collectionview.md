---
title: 'Vorgehensweise: Navigieren durch die Objekte in einer Datensammlungsansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 1507ab4db0c91b670d8bca754f6fd67d887c7041
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138176"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="79049-102">Vorgehensweise: Navigieren durch die Objekte in einer Datensammlungsansicht</span><span class="sxs-lookup"><span data-stu-id="79049-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="79049-103">Sichten können die Datenerfassung auf unterschiedliche Weise je nach Sortierung, Filterung oder Gruppierung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="79049-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="79049-104">Ansichten auch ein Konzept für aktuellen Datensatz Zeiger bereitstellen und aktivieren Sie den Zeiger bewegen.</span><span class="sxs-lookup"><span data-stu-id="79049-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="79049-105">Dieses Beispiel zeigt, wie Sie das aktuelle Objekt abgerufen sowie zum Navigieren durch die Objekte in einer Datensammlung, die die Funktion verwenden, der <xref:System.Windows.Data.CollectionView> Klasse.</span><span class="sxs-lookup"><span data-stu-id="79049-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79049-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79049-106">Example</span></span>  
 <span data-ttu-id="79049-107">In diesem Beispiel `myCollectionView` ist eine <xref:System.Windows.Data.CollectionView> -Objekt, das eine Ansicht für eine gebundene Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="79049-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="79049-108">Im folgenden Beispiel `OnButton` ist ein Ereignishandler für die `Previous` und `Next` Schaltflächen in einer Anwendung, die Schaltflächen sind, mit denen den Benutzer die Datensammlung navigieren können.</span><span class="sxs-lookup"><span data-stu-id="79049-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="79049-109">Beachten Sie, dass die <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> und <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> Eigenschaften Berichten, ob der Zeiger für der aktuelle Datensatz am Anfang und Ende der Liste also, das hat <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> und <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> kann je nach Bedarf aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="79049-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="79049-110">Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A> -Eigenschaft der Ansicht umgewandelt ist ein `Order` auf das aktuelle Element der Reihenfolge in der Auflistung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="79049-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="79049-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79049-111">See also</span></span>

- [<span data-ttu-id="79049-112">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="79049-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="79049-113">Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="79049-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="79049-114">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="79049-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="79049-115">Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="79049-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="79049-116">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="79049-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
