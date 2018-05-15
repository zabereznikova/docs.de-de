---
title: 'Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 15a7562efd9a86a029754610ffd9e77c372d1ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="e9ad2-102">Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="e9ad2-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="e9ad2-103">Verwenden Sie das folgende Verfahren um zu erkennen, wenn der Mauszeiger über ein <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="e9ad2-104">Erkennen, wenn der Mauszeiger über einem ToolStripItem befindet</span><span class="sxs-lookup"><span data-stu-id="e9ad2-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="e9ad2-105">Verwenden der <xref:System.Windows.Forms.ToolStripItem.Selected%2A> für Elemente in der Eigenschaft <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="e9ad2-106">Dadurch wird verhindert, Sie synchronisieren müssen die <xref:System.Windows.Forms.ToolStripItem.MouseEnter> und <xref:System.Windows.Forms.ToolStripItem.MouseLeave> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ad2-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9ad2-107">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [<span data-ttu-id="e9ad2-108">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e9ad2-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
