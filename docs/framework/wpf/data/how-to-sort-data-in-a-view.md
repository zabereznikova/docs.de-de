---
title: 'Gewusst wie: Sortieren von Daten in einer Ansicht'
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
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c39cec8aaf12b268790c19751562b16fa34cfdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="fc420-102">Gewusst wie: Sortieren von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="fc420-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="fc420-103">In diesem Beispiel wird das Sortieren von Daten in einer Ansicht beschreibt.</span><span class="sxs-lookup"><span data-stu-id="fc420-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc420-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc420-104">Example</span></span>  
 <span data-ttu-id="fc420-105">Das folgende Beispiel erstellt eine einfache <xref:System.Windows.Controls.ListBox> und ein <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="fc420-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="fc420-106">Die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der Schaltfläche enthält die Logik zum Sortieren der Elemente in der <xref:System.Windows.Controls.ListBox> in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fc420-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="fc420-107">Hierzu können Sie da Elemente hinzufügen einer <xref:System.Windows.Controls.ListBox> auf diese Weise hinzugefügt der <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Controls.ListBox>, und <xref:System.Windows.Controls.ItemCollection> leitet sich von der <xref:System.Windows.Data.CollectionView> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc420-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="fc420-108">Wenn Sie binden Ihrer <xref:System.Windows.Controls.ListBox> zu einer Sammlung mit den <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft, können Sie das gleiche Verfahren zum Sortieren.</span><span class="sxs-lookup"><span data-stu-id="fc420-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="fc420-109">Solange Sie einen Verweis auf das Ansichtsobjekt verfügen, können Sie das gleiche Verfahren, um den Inhalt der anderen Auflistungsansichten zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="fc420-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="fc420-110">Ein Beispiel zum Abrufen einer Ansicht finden Sie unter [die Standardansicht einer Datensammlung erhalten](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="fc420-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="fc420-111">Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView Spalte bei einem Header geklickt wird](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="fc420-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="fc420-112">Weitere Informationen zu Ansichten finden Sie unter Bindung für Sammlungen im [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fc420-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="fc420-113">Ein Beispiel zum Sortierfunktionen in Anwenden von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], finden Sie unter [sortieren und Gruppe mithilfe einer Sicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="fc420-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc420-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc420-114">See Also</span></span>  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [<span data-ttu-id="fc420-115">Sortieren einer GridView-Spalte beim Klicken auf einen Header</span><span class="sxs-lookup"><span data-stu-id="fc420-115">Sort a GridView Column When a Header Is Clicked</span></span>](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [<span data-ttu-id="fc420-116">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="fc420-116">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fc420-117">Filtern von Daten in einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="fc420-117">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="fc420-118">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="fc420-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
