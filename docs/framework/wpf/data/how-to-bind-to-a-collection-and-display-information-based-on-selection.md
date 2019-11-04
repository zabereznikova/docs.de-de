---
title: 'Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl'
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
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459145"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="07fad-102">Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="07fad-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="07fad-103">In einem einfachen Master/Detail-Szenario verfügen Sie über eine Daten gebundene <xref:System.Windows.Controls.ItemsControl> z. b. eine <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="07fad-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="07fad-104">Basierend auf der Benutzer Auswahl zeigen Sie weitere Informationen über das ausgewählte Element an.</span><span class="sxs-lookup"><span data-stu-id="07fad-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="07fad-105">In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="07fad-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07fad-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07fad-106">Example</span></span>  
 <span data-ttu-id="07fad-107">In diesem Beispiel ist `People` ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person` Klassen.</span><span class="sxs-lookup"><span data-stu-id="07fad-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="07fad-108">Diese `Person` Klasse enthält drei Eigenschaften: `FirstName`, `LastName`und `HomeTown`, alle vom Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="07fad-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="07fad-109">Der <xref:System.Windows.Controls.ContentControl> verwendet den folgenden <xref:System.Windows.DataTemplate>, der definiert, wie die Informationen eines `Person` dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="07fad-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="07fad-110">Im folgenden finden Sie einen Screenshot der Ergebnisse des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="07fad-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="07fad-111">In der <xref:System.Windows.Controls.ContentControl> werden die anderen Eigenschaften der ausgewählten Person angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07fad-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="07fad-112">![Binden an eine Sammlung](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="07fad-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="07fad-113">In diesem Beispiel sind die folgenden zwei Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="07fad-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="07fad-114">Der <xref:System.Windows.Controls.ListBox> und das <xref:System.Windows.Controls.ContentControl> an dieselbe Quelle gebunden.</span><span class="sxs-lookup"><span data-stu-id="07fad-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="07fad-115">Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften beider Bindungen werden nicht angegeben, weil beide Steuerelemente an das gesamte Sammlungsobjekt gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="07fad-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="07fad-116">Sie müssen die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>-Eigenschaft auf `true` festlegen, damit dies funktioniert.</span><span class="sxs-lookup"><span data-stu-id="07fad-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="07fad-117">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="07fad-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="07fad-118">Wenn das <xref:System.Windows.Controls.ListBox> die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>abruft, werden die Auswahl und die Währung Alternativ automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="07fad-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="07fad-119">Beachten Sie, dass die `Person`-Klasse die `ToString`-Methode wie folgt überschreibt.</span><span class="sxs-lookup"><span data-stu-id="07fad-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="07fad-120">Standardmäßig ruft der <xref:System.Windows.Controls.ListBox> `ToString` auf und zeigt eine Zeichen folgen Darstellung jedes Objekts in der gebundenen Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="07fad-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="07fad-121">Aus diesem Grund wird jede `Person` als Vorname in der <xref:System.Windows.Controls.ListBox>angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07fad-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="07fad-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07fad-122">See also</span></span>

- [<span data-ttu-id="07fad-123">Verwenden des Master-/Detailmusters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="07fad-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="07fad-124">Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="07fad-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="07fad-125">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="07fad-125">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="07fad-126">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="07fad-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="07fad-127">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="07fad-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
