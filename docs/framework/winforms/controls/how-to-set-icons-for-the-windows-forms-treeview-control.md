---
title: 'Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: b732aa510be22f3cbdc5197574f1e2a825c35df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536484"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="de05a-102">Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de05a-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="de05a-103">Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement Symbole neben den einzelnen Knoten können angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="de05a-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="de05a-104">Die Symbole werden unmittelbar links von den Knotentext positioniert.</span><span class="sxs-lookup"><span data-stu-id="de05a-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="de05a-105">Um diese Symbole anzuzeigen, müssen Sie die Strukturansicht mit Zuordnen einer <xref:System.Windows.Forms.ImageList> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="de05a-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="de05a-106">Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="de05a-106">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de05a-107">Ein Fehler in Microsoft .NET Framework, Version 1.1 wird verhindert, dass Bilder enthalten sind, auf <xref:System.Windows.Forms.TreeView> Knoten, wenn die Anwendung aufruft <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de05a-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de05a-108">Um diesen Fehler zu umgehen, rufen <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in Ihrer `Main` Methode sofort nach dem Aufruf <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="de05a-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="de05a-109">Dieser Fehler weist ein festes [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de05a-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="de05a-110">Anzeige von Bildern in einer Strukturansicht an</span><span class="sxs-lookup"><span data-stu-id="de05a-110">To display images in a tree view</span></span>  
  
1.  <span data-ttu-id="de05a-111">Legen Sie die <xref:System.Windows.Forms.TreeView> des Steuerelements <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft, um die vorhandene <xref:System.Windows.Forms.ImageList> Steuerelement, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="de05a-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="de05a-112">Diese Eigenschaften können im Designer mit dem Eigenschaftenfenster oder im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="de05a-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  <span data-ttu-id="de05a-113">Legen Sie des Knotens <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="de05a-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="de05a-114">Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> Eigenschaft bestimmt, das für den Knoten normalen und erweiterten Status angezeigte Bild und die <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> -Eigenschaft bestimmt das Bild für den ausgewählten Zustand des Knotens angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de05a-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="de05a-115">Diese Eigenschaften können im Code oder innerhalb des TreeNode-Editors festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="de05a-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="de05a-116">Um den TreeNode-Editor zu öffnen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( ![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft im Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="de05a-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="de05a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de05a-117">See Also</span></span>  
 [<span data-ttu-id="de05a-118">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="de05a-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="de05a-119">Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de05a-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="de05a-120">Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de05a-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="de05a-121">Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="de05a-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="de05a-122">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="de05a-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
