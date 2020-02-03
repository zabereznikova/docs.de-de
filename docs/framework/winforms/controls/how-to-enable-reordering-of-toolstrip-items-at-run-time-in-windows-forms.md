---
title: 'Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit'
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
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745475"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="5c964-102">Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c964-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="5c964-103">Sie können es dem Benutzer ermöglichen, <xref:System.Windows.Forms.ToolStripItem> Steuerelemente auf dem <xref:System.Windows.Forms.ToolStrip>neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="5c964-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="5c964-104">So aktivieren Sie die Neuanordnung von ToolStripItem zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5c964-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
- <span data-ttu-id="5c964-105">Setzen Sie die <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>-Eigenschaft auf `true`.</span><span class="sxs-lookup"><span data-stu-id="5c964-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="5c964-106">Standardmäßig ist <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> `false`.</span><span class="sxs-lookup"><span data-stu-id="5c964-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="5c964-107">Zur Laufzeit hält der Benutzer die Alt-Taste gedrückt und die linke Maustaste, um ein <xref:System.Windows.Forms.ToolStripItem> an einen anderen Speicherort auf dem <xref:System.Windows.Forms.ToolStrip>zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="5c964-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5c964-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c964-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="5c964-109">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5c964-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="5c964-110">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5c964-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="5c964-111">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="5c964-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
