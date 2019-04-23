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
ms.openlocfilehash: 1a857aade86d2366bb68ce14d716b3ce532ecb05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328412"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="c1bdb-102">Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1bdb-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="c1bdb-103">Die Windows-Formulare <xref:System.Windows.Forms.TreeView> -Steuerelement Symbole neben den einzelnen Knoten können angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="c1bdb-104">Die Symbole werden unmittelbar links neben den Knotentext positioniert.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="c1bdb-105">Um diese Symbole anzuzeigen, müssen Sie in der Strukturansicht mit Zuordnen einer <xref:System.Windows.Forms.ImageList> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="c1bdb-106">Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="c1bdb-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1bdb-107">Ein Fehler in Microsoft .NET Framework, Version 1.1 wird verhindert, dass es sich bei Bildern aus <xref:System.Windows.Forms.TreeView> Knoten aus, wenn die Anwendung aufruft <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c1bdb-108">Um dieses Problem zu umgehen, rufen Sie <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in Ihre `Main` Methode sofort nach dem Aufruf <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="c1bdb-109">Dieses Problem wurde behoben, im [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bdb-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="c1bdb-110">Zum Anzeigen von Bildern in einer Strukturansicht</span><span class="sxs-lookup"><span data-stu-id="c1bdb-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="c1bdb-111">Legen Sie die <xref:System.Windows.Forms.TreeView> des Steuerelements <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft, um die vorhandene <xref:System.Windows.Forms.ImageList> Kontrolle, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="c1bdb-112">Diese Eigenschaften können im Designer mit dem Fenster "Eigenschaften" oder im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="c1bdb-113">Festlegen des Knotens <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="c1bdb-114">Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> Eigenschaft bestimmt, das für den normalen und erweiterten Status des Knotens angezeigte Bild und die <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> Eigenschaft bestimmt, das für den ausgewählten Zustand des Knotens angezeigte Bild.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="c1bdb-115">Diese Eigenschaften können im Code oder in der TreeNode-Editor festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="c1bdb-116">Um die TreeNode-Editor zu öffnen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( ![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft im Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="c1bdb-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1bdb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1bdb-117">See also</span></span>

- [<span data-ttu-id="c1bdb-118">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c1bdb-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="c1bdb-119">Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1bdb-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="c1bdb-120">Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="c1bdb-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="c1bdb-121">Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="c1bdb-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="c1bdb-122">Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c1bdb-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
