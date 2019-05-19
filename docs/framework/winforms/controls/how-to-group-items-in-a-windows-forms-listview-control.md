---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: bbca1d76f747f53103095c916605ce7335207f51
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882373"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="74718-102">Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="74718-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="74718-103">Mit der Grouping-Funktion von der <xref:System.Windows.Forms.ListView> -Steuerelement, können Sie verwandte Elemente in Gruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="74718-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="74718-104">Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten.</span><span class="sxs-lookup"><span data-stu-id="74718-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="74718-105">Sie können <xref:System.Windows.Forms.ListView> Gruppen zum Navigieren in umfangreichen Listen einfacher durch Gruppieren von Elementen alphabetisch nach Datum oder eine beliebige andere logische Gruppierung.</span><span class="sxs-lookup"><span data-stu-id="74718-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="74718-106">Die folgende Abbildung zeigt einige gruppierte Elemente.</span><span class="sxs-lookup"><span data-stu-id="74718-106">The following image shows some grouped items.</span></span>  
  
 ![Screenshot der geraden und ungeraden ListView-Gruppen.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="74718-108">Aktivieren der Gruppierung, müssen Sie zunächst eine oder mehrere Gruppen im Designer oder programmgesteuert erstellen.</span><span class="sxs-lookup"><span data-stu-id="74718-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="74718-109">Nachdem eine Gruppe definiert wurde, können Sie zuweisen <xref:System.Windows.Forms.ListView> Elemente, die Gruppen.</span><span class="sxs-lookup"><span data-stu-id="74718-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="74718-110">Sie können auch Elemente aus einer Gruppe in eine andere programmgesteuert verschieben.</span><span class="sxs-lookup"><span data-stu-id="74718-110">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74718-111"><xref:System.Windows.Forms.ListView> Gruppen stehen nur auf [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] bei einem Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="74718-111"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="74718-112">Unter früheren Betriebssystemen Code im Zusammenhang mit Gruppen hat keine Auswirkungen, und die Gruppen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74718-112">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="74718-113">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74718-113">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="74718-114">Beim Hinzufügen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="74718-114">To add groups</span></span>  
  
1. <span data-ttu-id="74718-115">Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> -Methode der <xref:System.Windows.Forms.ListView.Groups%2A> -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="74718-115">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="74718-116">Gruppen entfernen</span><span class="sxs-lookup"><span data-stu-id="74718-116">To remove groups</span></span>  
  
1. <span data-ttu-id="74718-117">Verwenden der <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> oder <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> Methode der <xref:System.Windows.Forms.ListView.Groups%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="74718-117">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="74718-118">Die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Methode wird eine einzelne Gruppe entfernt; die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> -Methode entfernt alle Gruppen aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="74718-118">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74718-119">Eine Gruppe entfernen, wird die Elemente in dieser Gruppe nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="74718-119">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="74718-120">Zuweisen zu Gruppen von Elementen oder Elemente zwischen den Gruppen verschieben.</span><span class="sxs-lookup"><span data-stu-id="74718-120">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="74718-121">Legen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> -Eigenschaft einzelner Elemente.</span><span class="sxs-lookup"><span data-stu-id="74718-121">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="74718-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74718-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="74718-123">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74718-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="74718-124">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74718-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="74718-125">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="74718-125">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
