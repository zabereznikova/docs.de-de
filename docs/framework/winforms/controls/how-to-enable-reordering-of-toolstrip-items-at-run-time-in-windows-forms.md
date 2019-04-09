---
title: 'Vorgehensweise: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: daff9d6d351db514d552225853f977775f8e3204
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220401"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="ecbcc-102">Vorgehensweise: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ecbcc-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="ecbcc-103">Sie können die Benutzer zum Ändern der Anordnung ermöglichen <xref:System.Windows.Forms.ToolStripItem> steuert, auf die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ecbcc-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="ecbcc-104">ToolStripItem-neuanordnung zur Laufzeit zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="ecbcc-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="ecbcc-105">Legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="ecbcc-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="ecbcc-106">In der Standardeinstellung <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ecbcc-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="ecbcc-107">Zur Laufzeit wird der Benutzer hält die ALT-Taste und die linke Maustaste gedrückt, ziehen eine <xref:System.Windows.Forms.ToolStripItem> an einen anderen Speicherort auf dem <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ecbcc-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ecbcc-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecbcc-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="ecbcc-109">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ecbcc-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="ecbcc-110">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ecbcc-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="ecbcc-111">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="ecbcc-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
