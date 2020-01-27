---
title: Anzeigen von Symbolen für das ListView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744501"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="17186-102">Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="17186-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="17186-103">Das Windows Forms <xref:System.Windows.Forms.ListView>-Steuerelement kann Symbole aus drei Bildlisten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="17186-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="17186-104">In den Ansichten List, Details und SmallIcon werden Bilder aus der Bildliste angezeigt, die in der <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="17186-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="17186-105">In der LargeIcon-Ansicht werden Bilder aus der Bildliste angezeigt, die in der <xref:System.Windows.Forms.ListView.LargeImageList%2A>-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="17186-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="17186-106">In einer Listenansicht kann auch ein zusätzlicher Satz von Symbolen angezeigt werden, der in der <xref:System.Windows.Forms.ListView.StateImageList%2A>-Eigenschaft neben den großen oder kleinen Symbolen festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="17186-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="17186-107">Weitere Informationen zu Bildlisten finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und Gewusst [wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="17186-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="17186-108">So zeigen Sie Bilder in einer Listenansicht an</span><span class="sxs-lookup"><span data-stu-id="17186-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="17186-109">Legen Sie die entsprechende Eigenschaft –<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>oder <xref:System.Windows.Forms.ListView.StateImageList%2A>– auf die vorhandene <xref:System.Windows.Forms.ImageList> Komponente fest, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="17186-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="17186-110">Diese Eigenschaften können im Designer mit dem Eigenschaftenfenster oder im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="17186-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="17186-111">Legen Sie die Eigenschaft <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> oder <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> für jedes Listenelement mit einem zugeordneten Symbol fest.</span><span class="sxs-lookup"><span data-stu-id="17186-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="17186-112">Diese Eigenschaften können im Code oder im **ListViewItem-Auflistungs-Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="17186-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="17186-113">Um den **ListViewItem-Auflistungs-Editor**zu öffnen, klicken Sie auf die Schaltfläche mit den Auslassungs Zeichen![(...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft im **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="17186-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="17186-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17186-114">See also</span></span>

- [<span data-ttu-id="17186-115">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="17186-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="17186-116">Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="17186-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="17186-117">Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="17186-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="17186-118">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="17186-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="17186-119">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="17186-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
