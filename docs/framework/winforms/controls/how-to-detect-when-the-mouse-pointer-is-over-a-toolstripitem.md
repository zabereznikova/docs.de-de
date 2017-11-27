---
title: 'Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 633b92bf6da837b3727001c621548fa58b230102
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="d6529-102">Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="d6529-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="d6529-103">Verwenden Sie das folgende Verfahren um zu erkennen, wenn der Mauszeiger über ein <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="d6529-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="d6529-104">Erkennen, wenn der Mauszeiger über einem ToolStripItem befindet</span><span class="sxs-lookup"><span data-stu-id="d6529-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="d6529-105">Verwenden der <xref:System.Windows.Forms.ToolStripItem.Selected%2A> für Elemente in der Eigenschaft <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="d6529-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="d6529-106">Dadurch wird verhindert, Sie synchronisieren müssen die <xref:System.Windows.Forms.ToolStripItem.MouseEnter> und <xref:System.Windows.Forms.ToolStripItem.MouseLeave> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d6529-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6529-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6529-107">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [<span data-ttu-id="d6529-108">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d6529-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
