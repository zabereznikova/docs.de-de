---
title: 'Gewusst wie: Sortieren von Daten in einer Ansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 14314ed019f9194a657787bd767ae68615e94ac7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454824"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="1ed3e-102">Gewusst wie: Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="1ed3e-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="1ed3e-103">In diesem Beispiel wird beschrieben, wie Daten in einer Ansicht sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ed3e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ed3e-104">Example</span></span>  
 <span data-ttu-id="1ed3e-105">Im folgenden Beispiel werden eine einfache <xref:System.Windows.Controls.ListBox> und eine <xref:System.Windows.Controls.Button>erstellt:</span><span class="sxs-lookup"><span data-stu-id="1ed3e-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="1ed3e-106">Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignishandler der Schaltfläche enthält Logik zum Sortieren der Elemente in der <xref:System.Windows.Controls.ListBox> in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="1ed3e-107">Dies ist möglich, weil Sie Elemente zu einem <xref:System.Windows.Controls.ListBox> hinzufügen, um diese auf diese Weise dem <xref:System.Windows.Controls.ItemCollection> des <xref:System.Windows.Controls.ListBox>hinzuzufügen, und <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Data.CollectionView> Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="1ed3e-108">Wenn Sie die <xref:System.Windows.Controls.ListBox> mit der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft an eine Sammlung binden, können Sie das gleiche Verfahren für die Sortierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="1ed3e-109">Solange Sie über einen Verweis auf das Ansichts Objekt verfügen, können Sie das gleiche Verfahren verwenden, um den Inhalt anderer Auflistungs Ansichten zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="1ed3e-110">Ein Beispiel zum Abrufen einer Ansicht finden Sie unter Abrufen [der Standardansicht einer Datensammlung](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="1ed3e-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="1ed3e-111">Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="1ed3e-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="1ed3e-112">Weitere Informationen zu Ansichten finden Sie unterbinden an Auflistungen in der Übersicht über die [Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ed3e-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="1ed3e-113">Ein Beispiel für das Anwenden von Sortier Logik in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]finden Sie unter [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="1ed3e-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed3e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ed3e-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="1ed3e-115">Sortieren einer GridView-Spalte beim Klicken auf einen Header</span><span class="sxs-lookup"><span data-stu-id="1ed3e-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="1ed3e-116">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="1ed3e-116">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1ed3e-117">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="1ed3e-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="1ed3e-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1ed3e-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
