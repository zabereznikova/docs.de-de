---
title: 'Vorgehensweise: Erkennen des Mauszeigers auf einem ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220044"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="48dd8-102">Vorgehensweise: Erkennen des Mauszeigers auf einem ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="48dd8-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="48dd8-103">Verwenden Sie das folgende Verfahren, um die erkennen, wenn der Mauszeiger über einem <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="48dd8-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="48dd8-104">Erkennen, wenn der Mauszeiger über einem ToolStripItem befindet</span><span class="sxs-lookup"><span data-stu-id="48dd8-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="48dd8-105">Verwenden der <xref:System.Windows.Forms.ToolStripItem.Selected%2A> -Eigenschaft für Elemente, in denen <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="48dd8-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="48dd8-106">Dies hindert Sie synchronisieren müssen dem <xref:System.Windows.Forms.ToolStripItem.MouseEnter> und <xref:System.Windows.Forms.ToolStripItem.MouseLeave> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="48dd8-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48dd8-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48dd8-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="48dd8-108">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="48dd8-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
