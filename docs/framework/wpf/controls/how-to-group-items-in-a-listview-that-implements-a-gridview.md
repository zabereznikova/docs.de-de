---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView-Objekt, in dem ein GridView-Objekt implementiert ist'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910272"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="0a627-102">Vorgehensweise: Gruppieren von Elementen in einem ListView-Objekt, in dem ein GridView-Objekt implementiert ist</span><span class="sxs-lookup"><span data-stu-id="0a627-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="0a627-103">Dieses Beispiel zeigt die Vorgehensweise beim Anzeigen von Gruppen von Elementen auf der <xref:System.Windows.Controls.GridView> Ansichtsmodus des eine <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0a627-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a627-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a627-104">Example</span></span>  
 <span data-ttu-id="0a627-105">Zum Anzeigen von Gruppen von Elementen auf einer <xref:System.Windows.Controls.ListView>, definieren Sie eine <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="0a627-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="0a627-106">Das folgende Beispiel zeigt eine <xref:System.Windows.Data.CollectionViewSource> -Datenelemente entsprechend dem Wert der Gruppen, denen die `Catalog` Feld "Daten".</span><span class="sxs-lookup"><span data-stu-id="0a627-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="0a627-107">Im folgenden Beispiel wird die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.ListView> auf die <xref:System.Windows.Data.CollectionViewSource> , die im vorherige Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="0a627-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="0a627-108">Im Beispiel definiert auch eine <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> , implementiert eine <xref:System.Windows.Controls.Expander> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0a627-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="0a627-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a627-109">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="0a627-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0a627-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="0a627-111">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="0a627-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="0a627-112">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="0a627-112">GridView Overview</span></span>](gridview-overview.md)
