---
title: 'Vorgehensweise: Binden an eine Sammlung und Anzeigen von Informationen auf Grundlage der Auswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: bb7d4c89e63982a3052857dcb50d04d36d9517dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314390"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="b0304-102">Vorgehensweise: Binden an eine Sammlung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="b0304-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="b0304-103">In einem einfachen Master / Detail-Szenario haben Sie ein datengebundenes <xref:System.Windows.Controls.ItemsControl> wie z. B. eine <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="b0304-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="b0304-104">Auf Grundlage der Benutzerauswahl, zeigen Sie weitere Informationen zum ausgewählten Element.</span><span class="sxs-lookup"><span data-stu-id="b0304-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="b0304-105">Dieses Beispiel zeigt, wie Sie dieses Szenario zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b0304-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0304-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0304-106">Example</span></span>  
 <span data-ttu-id="b0304-107">In diesem Beispiel `People` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person` Klassen.</span><span class="sxs-lookup"><span data-stu-id="b0304-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="b0304-108">Dies `Person` -Klasse enthält drei Eigenschaften: `FirstName`, `LastName`, und `HomeTown`, alle Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="b0304-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="b0304-109">Die <xref:System.Windows.Controls.ContentControl> verwendet die folgenden <xref:System.Windows.DataTemplate> , definiert, wie die Informationen des eine `Person` wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b0304-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="b0304-110">Folgendes ist ein Screenshot der Ausgabe des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="b0304-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="b0304-111">Die <xref:System.Windows.Controls.ContentControl> zeigt die anderen Eigenschaften der ausgewählten Person.</span><span class="sxs-lookup"><span data-stu-id="b0304-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="b0304-112">![Binden an eine Auflistung](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="b0304-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="b0304-113">Die beiden in diesem Beispiel sind zu beachten:</span><span class="sxs-lookup"><span data-stu-id="b0304-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="b0304-114">Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ContentControl> an dieselbe Quelle binden.</span><span class="sxs-lookup"><span data-stu-id="b0304-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="b0304-115">Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften beide Bindungen sind nicht angegeben werden, da beide Steuerelemente an das gesamte Objekt gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="b0304-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="b0304-116">Sie müssen festlegen, die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` damit dies funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b0304-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="b0304-117">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0304-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="b0304-118">Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, diese Auswahl und Aktualität wird automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="b0304-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="b0304-119">Beachten Sie, dass die `Person` -Klasse überschreibt die `ToString` Methode wie folgt.</span><span class="sxs-lookup"><span data-stu-id="b0304-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="b0304-120">In der Standardeinstellung die <xref:System.Windows.Controls.ListBox> Aufrufe `ToString` und eine Zeichenfolgendarstellung der einzelnen Objekte in der gebundenen Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0304-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="b0304-121">Deshalb jedes `Person` wird als einen Vornamen in der <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="b0304-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="b0304-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0304-122">See also</span></span>

- [<span data-ttu-id="b0304-123">Verwenden des Master-/Detailmusters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="b0304-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="b0304-124">Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="b0304-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="b0304-125">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="b0304-125">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="b0304-126">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="b0304-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="b0304-127">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b0304-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
