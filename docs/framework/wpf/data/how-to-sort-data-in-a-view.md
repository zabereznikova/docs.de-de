---
title: 'Vorgehensweise: Sortieren von Daten in einer Ansicht'
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
ms.openlocfilehash: 50e1426f2a220c7d947f7feb9c3ec7e1c4de7643
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522673"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="1ddcf-102">Vorgehensweise: Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="1ddcf-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="1ddcf-103">In diesem Beispiel wird das Sortieren von Daten in einer Ansicht beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1ddcf-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ddcf-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ddcf-104">Example</span></span>  
 <span data-ttu-id="1ddcf-105">Das folgende Beispiel erstellt eine einfache <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="1ddcf-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="1ddcf-106">Die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der Schaltfläche enthält Logik zum Sortieren der Elemente in der <xref:System.Windows.Controls.ListBox> in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1ddcf-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="1ddcf-107">Hierzu können Sie da Hinzufügen von Elementen auf eine <xref:System.Windows.Controls.ListBox> auf diese Weise hinzugefügt der <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Controls.ListBox>, und <xref:System.Windows.Controls.ItemCollection> leitet sich von der <xref:System.Windows.Data.CollectionView> Klasse.</span><span class="sxs-lookup"><span data-stu-id="1ddcf-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="1ddcf-108">Wenn die Bindung wird Ihrer <xref:System.Windows.Controls.ListBox> zu einer Auflistung mithilfe der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft, können Sie das gleiche Verfahren zum Sortieren verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ddcf-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="1ddcf-109">Solange Sie einen Verweis auf das Objekt haben, können Sie das gleiche Verfahren, zum Sortieren des Inhalts einer anderen sammlungsansichten.</span><span class="sxs-lookup"><span data-stu-id="1ddcf-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="1ddcf-110">Ein Beispiel, wie Sie eine Ansicht zu erhalten, finden Sie unter [Abrufen der Standardansicht einer datenauflistung](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="1ddcf-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="1ddcf-111">Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView Spalte bei der ein Header geklickt wird](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="1ddcf-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="1ddcf-112">Weitere Informationen zu Ansichten finden Sie unter Binden an Auflistungen in [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ddcf-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="1ddcf-113">Ein Beispiel für die Sortierfunktionen in anwenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], finden Sie unter [sortieren und Daten mithilfe einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="1ddcf-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ddcf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ddcf-114">See also</span></span>
- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="1ddcf-115">Sortieren einer GridView-Spalte beim Klicken auf einen Header</span><span class="sxs-lookup"><span data-stu-id="1ddcf-115">Sort a GridView Column When a Header Is Clicked</span></span>](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="1ddcf-116">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="1ddcf-116">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1ddcf-117">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="1ddcf-117">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="1ddcf-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1ddcf-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
