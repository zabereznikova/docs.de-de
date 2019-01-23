---
title: 'Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 3c3df1fb38c9fbcf672e9ffcd8c0aa3c881be00b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510623"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="65dd8-102">Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65dd8-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="65dd8-103">Die Windows-Formulare <xref:System.Windows.Forms.ListView> Steuerelement kann Symbole aus einer Bildliste drei anzeigen.</span><span class="sxs-lookup"><span data-stu-id="65dd8-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="65dd8-104">Die Liste, Details und SmallIcon Ansichten anzeigen von Bildern aus der Liste der Bilder in angegebenen die <xref:System.Windows.Forms.ListView.SmallImageList%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="65dd8-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="65dd8-105">Die LargeIcon zeigt Bilder aus der Liste der Bilder in angegebenen die <xref:System.Windows.Forms.ListView.LargeImageList%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="65dd8-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="65dd8-106">Eine Listenansicht kann auch einen zusätzlichen Satz von Symbolen, legen Sie im Anzeigen der <xref:System.Windows.Forms.ListView.StateImageList%2A> neben den großen oder kleinen Symbolen-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="65dd8-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="65dd8-107">Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="65dd8-107">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="65dd8-108">Zum Anzeigen von Bildern in einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="65dd8-108">To display images in a list view</span></span>  
  
1.  <span data-ttu-id="65dd8-109">Legen Sie die entsprechende Eigenschaft –<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, oder <xref:System.Windows.Forms.ListView.StateImageList%2A>– mit dem vorhandenen <xref:System.Windows.Forms.ImageList> Komponente, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="65dd8-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="65dd8-110">Diese Eigenschaften können im Designer mit dem Fenster "Eigenschaften" oder im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="65dd8-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  <span data-ttu-id="65dd8-111">Legen Sie die <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> oder <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> -Eigenschaft für jedes Listenelement, das ein zugeordnetes Symbol verfügt.</span><span class="sxs-lookup"><span data-stu-id="65dd8-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="65dd8-112">Diese Eigenschaften können festgelegt werden, im Code oder in der **ListViewItem Auflistungs-Editor**.</span><span class="sxs-lookup"><span data-stu-id="65dd8-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="65dd8-113">Zum Öffnen der **ListViewItem Auflistungs-Editor**, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.ListView.Items%2A>Eigenschaft für die **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="65dd8-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="65dd8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65dd8-114">See also</span></span>
- [<span data-ttu-id="65dd8-115">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65dd8-115">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [<span data-ttu-id="65dd8-116">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65dd8-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="65dd8-117">Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65dd8-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="65dd8-118">Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="65dd8-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="65dd8-119">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="65dd8-119">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
