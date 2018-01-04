---
title: 'Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht'
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
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215e3583d50567a2bfec8226e006bc7398628299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="f9b87-102">Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht</span><span class="sxs-lookup"><span data-stu-id="f9b87-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="f9b87-103">Ansichten können die gleichen Datensammlung unterschiedlich, je nach sortieren, filtern oder gruppieren angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f9b87-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="f9b87-104">Ansichten auch Geben Sie einen aktuellen Datensatzzeiger Konzept und verschieben den Zeiger zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9b87-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="f9b87-105">In diesem Beispiel wird gezeigt, wie das aktuelle Objekt abgerufen sowie zum Navigieren durch die Objekte in einer Datensammlung, die mithilfe der Funktionen der <xref:System.Windows.Data.CollectionView> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f9b87-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9b87-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9b87-106">Example</span></span>  
 <span data-ttu-id="f9b87-107">In diesem Beispiel `myCollectionView` ist ein <xref:System.Windows.Data.CollectionView> -Objekt, das eine Ansicht für eine gebundene Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="f9b87-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="f9b87-108">Im folgenden Beispiel `OnButton` ist ein Ereignishandler für das `Previous` und `Next` Schaltflächen in einer Anwendung, die Schaltflächen sind, mit denen den Benutzer die Datensammlung navigieren können.</span><span class="sxs-lookup"><span data-stu-id="f9b87-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="f9b87-109">Beachten Sie, dass die <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> und <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> Eigenschaften Berichten, ob der Zeiger für der aktuelle Datensatz am Anfang und am Ende der Liste daher, die hat <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> und <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> kann je nach Bedarf aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f9b87-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="f9b87-110">Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A> -Eigenschaft der Ansicht umgewandelte ein `Order` auf das aktuelle Element der Reihenfolge in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f9b87-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="f9b87-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9b87-111">See Also</span></span>  
 [<span data-ttu-id="f9b87-112">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="f9b87-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f9b87-113">Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="f9b87-113">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="f9b87-114">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="f9b87-114">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="f9b87-115">Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="f9b87-115">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="f9b87-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f9b87-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
