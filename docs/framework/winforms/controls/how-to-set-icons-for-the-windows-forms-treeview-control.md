---
title: 'Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909811"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="1b8df-102">Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8df-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="1b8df-103">Das Windows Forms <xref:System.Windows.Forms.TreeView> Steuerelement kann Symbole neben den einzelnen Knoten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b8df-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="1b8df-104">Die Symbole werden direkt links neben dem Knoten Text positioniert.</span><span class="sxs-lookup"><span data-stu-id="1b8df-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="1b8df-105">Um diese Symbole anzuzeigen, müssen Sie die Strukturansicht einem <xref:System.Windows.Forms.ImageList> -Steuerelement zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1b8df-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="1b8df-106">Weitere Informationen zu Bildlisten finden Sie unter [ImageList](imagelist-component-windows-forms.md) -Komponente [und Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="1b8df-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b8df-107">Ein Fehler in Microsoft .NET Framework-Version 1,1 verhindert, dass Bilder <xref:System.Windows.Forms.TreeView> auf Knoten angezeigt werden, <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>wenn die Anwendung aufruft.</span><span class="sxs-lookup"><span data-stu-id="1b8df-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1b8df-108">Um diesen Fehler zu umgehen, rufen <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> Sie direkt `Main` nach dem Aufrufen <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>von in ihrer-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="1b8df-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="1b8df-109">Dieser Fehler wurde in .NET Framework 2,0 behoben.</span><span class="sxs-lookup"><span data-stu-id="1b8df-109">This bug is fixed in .NET Framework 2.0.</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="1b8df-110">So zeigen Sie Bilder in einer Strukturansicht an</span><span class="sxs-lookup"><span data-stu-id="1b8df-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="1b8df-111">Legen Sie <xref:System.Windows.Forms.TreeView> die- <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft des Steuer Elements <xref:System.Windows.Forms.ImageList> auf das vorhandene Steuerelement fest, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1b8df-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="1b8df-112">Diese Eigenschaften können im Designer mit dem Eigenschaftenfenster oder im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1b8df-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="1b8df-113">Legen Sie die Eigenschaften <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> des Knotens fest.</span><span class="sxs-lookup"><span data-stu-id="1b8df-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="1b8df-114">Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> -Eigenschaft bestimmt das Bild, das für den normalen und erweiterten Status des Knotens <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> angezeigt wird, und die-Eigenschaft bestimmt das Bild, das für den ausgewählten Status des Knotens angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1b8df-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="1b8df-115">Diese Eigenschaften können im Code oder im TreeNode-Editor festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1b8df-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="1b8df-116">Um den TreeNode-Editor zu öffnen, klicken Sie auf die ![Schaltfläche mit den Auslassungs Zeichen (...) im Eigenschaftenfenster von Visual](./media/visual-studio-ellipsis-button.png)Studio.) neben <xref:System.Windows.Forms.TreeView.Nodes%2A> der-Eigenschaft auf der Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="1b8df-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b8df-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b8df-117">See also</span></span>

- [<span data-ttu-id="1b8df-118">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1b8df-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="1b8df-119">Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem Windows Forms TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1b8df-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="1b8df-120">Vorgehensweise: Iterieren aller Knoten eines Windows Forms TreeView-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="1b8df-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="1b8df-121">Vorgehensweise: Ermitteln, auf welchen TreeView-Knoten geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="1b8df-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="1b8df-122">Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1b8df-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
