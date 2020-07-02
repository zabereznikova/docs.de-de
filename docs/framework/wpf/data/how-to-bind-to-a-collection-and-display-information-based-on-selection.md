---
title: 'Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl'
description: In diesem Beispiel erfahren Sie, wie Sie eine Bindung an eine Sammlung durchführen und Informationen basierend auf der Auswahl im Windows Presentation Foundation (WPF) anzeigen.
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
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619610"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="ee704-103">Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="ee704-103">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="ee704-104">In einem einfachen Master/Detail-Szenario verfügen Sie über eine Daten gebundene, <xref:System.Windows.Controls.ItemsControl> z <xref:System.Windows.Controls.ListBox> . b..</span><span class="sxs-lookup"><span data-stu-id="ee704-104">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="ee704-105">Basierend auf der Benutzer Auswahl zeigen Sie weitere Informationen über das ausgewählte Element an.</span><span class="sxs-lookup"><span data-stu-id="ee704-105">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="ee704-106">In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee704-106">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee704-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee704-107">Example</span></span>  
 <span data-ttu-id="ee704-108">In diesem Beispiel `People` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von- `Person` Klassen.</span><span class="sxs-lookup"><span data-stu-id="ee704-108">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="ee704-109">Diese `Person` Klasse enthält drei Eigenschaften: `FirstName` , `LastName` und `HomeTown` alle vom Typ `string` .</span><span class="sxs-lookup"><span data-stu-id="ee704-109">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="ee704-110">Der <xref:System.Windows.Controls.ContentControl> verwendet Folgendes <xref:System.Windows.DataTemplate> , das definiert, wie die Informationen eines `Person` dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="ee704-110">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="ee704-111">Im folgenden finden Sie einen Screenshot der Ergebnisse des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="ee704-111">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="ee704-112">Die <xref:System.Windows.Controls.ContentControl> zeigt die anderen Eigenschaften der ausgewählten Person an.</span><span class="sxs-lookup"><span data-stu-id="ee704-112">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="ee704-113">![Binden an eine Auflistung](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="ee704-113">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="ee704-114">In diesem Beispiel sind die folgenden zwei Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="ee704-114">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="ee704-115"><xref:System.Windows.Controls.ListBox>Und die <xref:System.Windows.Controls.ContentControl> an dieselbe Quelle binden.</span><span class="sxs-lookup"><span data-stu-id="ee704-115">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="ee704-116">Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften beider Bindungen werden nicht angegeben, weil beide Steuerelemente an das gesamte Sammlungsobjekt gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="ee704-116">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="ee704-117">Sie müssen die- <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft auf festlegen, damit `true` Dies funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ee704-117">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="ee704-118">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als festgelegt ist <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> .</span><span class="sxs-lookup"><span data-stu-id="ee704-118">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="ee704-119">Wenn die <xref:System.Windows.Controls.ListBox> Daten aus einem abruft, werden die <xref:System.Windows.Data.CollectionViewSource> Auswahl und die Währung Alternativ automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="ee704-119">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="ee704-120">Beachten Sie, dass die-Klasse die- `Person` `ToString` Methode wie folgt überschreibt.</span><span class="sxs-lookup"><span data-stu-id="ee704-120">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="ee704-121">Standardmäßig wird von <xref:System.Windows.Controls.ListBox> aufgerufen `ToString` und eine Zeichen folgen Darstellung der einzelnen Objekte in der gebundenen Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee704-121">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="ee704-122">Daher wird jeder `Person` als Vorname in der angezeigt <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="ee704-122">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="ee704-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee704-123">See also</span></span>

- [<span data-ttu-id="ee704-124">Verwenden des Master/Detail-Musters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="ee704-124">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="ee704-125">Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="ee704-125">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="ee704-126">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="ee704-126">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ee704-127">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="ee704-127">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="ee704-128">Artikel zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="ee704-128">How-to Topics</span></span>](data-binding-how-to-topics.md)
