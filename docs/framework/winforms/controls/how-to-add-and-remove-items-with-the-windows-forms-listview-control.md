---
title: Hinzufügen und Entfernen von Elementen mit ListView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: bbfe99db857ebe3a80bf99926f3ce0bec38a1f3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743142"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="ef1ae-102">Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef1ae-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="ef1ae-103">Das Hinzufügen eines Elements zu einem Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement besteht hauptsächlich darin, das Element anzugeben und ihm Eigenschaften zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ef1ae-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="ef1ae-104">Das Hinzufügen oder Entfernen von Listenelementen ist jederzeit möglich.</span><span class="sxs-lookup"><span data-stu-id="ef1ae-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="ef1ae-105">So fügen Sie Elemente Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="ef1ae-105">To add items programmatically</span></span>  
  
1. <span data-ttu-id="ef1ae-106">Verwenden Sie die <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A>-Methode der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ef1ae-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="ef1ae-107">So entfernen Sie Elemente Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="ef1ae-107">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="ef1ae-108">Verwenden Sie die <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>-oder <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>-Methode der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ef1ae-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="ef1ae-109">Die <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>-Methode entfernt ein einzelnes Element. mit der <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>-Methode werden alle Elemente aus der Liste entfernt.</span><span class="sxs-lookup"><span data-stu-id="ef1ae-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="ef1ae-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef1ae-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="ef1ae-111">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ef1ae-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="ef1ae-112">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ef1ae-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
