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
ms.openlocfilehash: b4cd2b9ed23f377912270d33b1415ad39c9e80c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966633"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="ad6e6-102">Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad6e6-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="ad6e6-103">Mit der Gruppierungs Funktion des <xref:System.Windows.Forms.ListView> Steuer Elements können Sie Verwandte Gruppen von Elementen in Gruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="ad6e6-104">Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppen Kopfzeilen getrennt, die die Gruppentitel enthalten.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="ad6e6-105">Mithilfe von <xref:System.Windows.Forms.ListView> Gruppen können Sie die Navigation durch große Listen vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach einer anderen logischen Gruppierung gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="ad6e6-106">Die folgende Abbildung zeigt einige gruppierte Elemente.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-106">The following image shows some grouped items.</span></span>  
  
 ![Screenshot von ungeraden und geraden ListView-Gruppen.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="ad6e6-108">Um die Gruppierung zu aktivieren, müssen Sie zuerst eine oder mehrere Gruppen entweder im Designer oder Programm gesteuert erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="ad6e6-109">Nachdem eine Gruppe definiert wurde, können Sie Gruppenelemente <xref:System.Windows.Forms.ListView> zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="ad6e6-110">Sie können Elemente auch Programm gesteuert aus einer Gruppe in eine andere verschieben.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-110">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad6e6-111"><xref:System.Windows.Forms.ListView>Gruppen sind nur in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] verfügbar, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> -Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-111"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ad6e6-112">Unter früheren Betriebssystemen hat Code in Bezug auf Gruppen keine Auswirkung, und die Gruppen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-112">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="ad6e6-113">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-113">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="ad6e6-114">So fügen Sie Gruppen hinzu</span><span class="sxs-lookup"><span data-stu-id="ad6e6-114">To add groups</span></span>  
  
1. <span data-ttu-id="ad6e6-115">Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> -Methode der <xref:System.Windows.Forms.ListView.Groups%2A> -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-115">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="ad6e6-116">So entfernen Sie Gruppen</span><span class="sxs-lookup"><span data-stu-id="ad6e6-116">To remove groups</span></span>  
  
1. <span data-ttu-id="ad6e6-117">Verwenden Sie <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> -oder- <xref:System.Windows.Forms.ListView.Groups%2A> Methode der-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-117">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="ad6e6-118">Mit <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> der-Methode wird eine einzelne Gruppe <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> entfernt; die-Methode entfernt alle Gruppen aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-118">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad6e6-119">Durch das Entfernen einer Gruppe werden die Elemente in dieser Gruppe nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-119">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="ad6e6-120">So weisen Sie Gruppenelemente zu oder Verschieben Elemente zwischen Gruppen</span><span class="sxs-lookup"><span data-stu-id="ad6e6-120">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="ad6e6-121">Legen Sie <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> die-Eigenschaft einzelner Elemente fest.</span><span class="sxs-lookup"><span data-stu-id="ad6e6-121">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="ad6e6-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad6e6-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="ad6e6-123">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ad6e6-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="ad6e6-124">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ad6e6-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="ad6e6-125">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem Windows Forms ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ad6e6-125">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
