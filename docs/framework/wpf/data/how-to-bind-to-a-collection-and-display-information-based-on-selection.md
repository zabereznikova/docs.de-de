---
title: 'Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl'
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
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a751025470b566ef1e735e4ddd192cfd8fc354ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="93aee-102">Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="93aee-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="93aee-103">In einem einfachen Master / Detail-Szenario haben Sie ein datengebundenes <xref:System.Windows.Controls.ItemsControl> wie z. B. eine <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="93aee-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="93aee-104">Basierend auf der Auswahl des Benutzers, zeigen Sie weitere Informationen zum ausgewählten Element.</span><span class="sxs-lookup"><span data-stu-id="93aee-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="93aee-105">In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="93aee-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93aee-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93aee-106">Example</span></span>  
 <span data-ttu-id="93aee-107">In diesem Beispiel `People` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person` Klassen.</span><span class="sxs-lookup"><span data-stu-id="93aee-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="93aee-108">Dies `Person` Klasse enthält drei Eigenschaften: `FirstName`, `LastName`, und `HomeTown`, alle vom Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="93aee-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="93aee-109">Die <xref:System.Windows.Controls.ContentControl> verwendet die folgenden <xref:System.Windows.DataTemplate> , definiert, wie die Informationen des ein `Person` wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="93aee-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="93aee-110">Im folgenden finden einen Screenshot der Ausgabe des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="93aee-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="93aee-111">Die <xref:System.Windows.Controls.ContentControl> zeigt die anderen Eigenschaften der ausgewählten Person.</span><span class="sxs-lookup"><span data-stu-id="93aee-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="93aee-112">![Binden an eine Auflistung](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="93aee-112">![Binding to a collection](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="93aee-113">Die zwei Punkte zu beachten in diesem Beispiel sind:</span><span class="sxs-lookup"><span data-stu-id="93aee-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="93aee-114">Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ContentControl> mit der gleichen Quelle zu binden.</span><span class="sxs-lookup"><span data-stu-id="93aee-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="93aee-115">Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften der beiden Bindungen sind nicht angegeben werden, da beide Steuerelemente an das gesamte Collection-Objekt gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="93aee-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="93aee-116">Sie müssen festlegen, die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` damit dies funktioniert.</span><span class="sxs-lookup"><span data-stu-id="93aee-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="93aee-117">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="93aee-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="93aee-118">Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, es Auswahl und Währung automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="93aee-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="93aee-119">Beachten Sie, dass die `Person` -Klasse überschreibt die `ToString` Methode wie folgt.</span><span class="sxs-lookup"><span data-stu-id="93aee-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="93aee-120">Wird standardmäßig die <xref:System.Windows.Controls.ListBox> Aufrufe `ToString` und eine Zeichenfolgendarstellung für jedes Objekt in der gebundenen Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93aee-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="93aee-121">Deshalb jedes `Person` erscheint als erste Name in der <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="93aee-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="93aee-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93aee-122">See Also</span></span>  
 [<span data-ttu-id="93aee-123">Verwenden des Master-/Detailmusters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="93aee-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [<span data-ttu-id="93aee-124">Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="93aee-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [<span data-ttu-id="93aee-125">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="93aee-125">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="93aee-126">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="93aee-126">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="93aee-127">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="93aee-127">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
