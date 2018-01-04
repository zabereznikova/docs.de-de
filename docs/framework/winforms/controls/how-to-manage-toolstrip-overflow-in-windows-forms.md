---
title: "Gewusst wie: Umgang mit dem ToolStrip-Überlauf in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 619c4832626693a56280c70af3ade5dbb9e9d4de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="3039f-102">Gewusst wie: Umgang mit dem ToolStrip-Überlauf in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3039f-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>
<span data-ttu-id="3039f-103">Wenn alle Elemente in einer <xref:System.Windows.Forms.ToolStrip> Steuerelement in den zugewiesenen Speicherplatz nicht passen, können Sie Überlauffunktion aktivieren, auf die <xref:System.Windows.Forms.ToolStrip> und bestimmen das Überlaufverhalten bei bestimmten <xref:System.Windows.Forms.ToolStripItem>s.</span><span class="sxs-lookup"><span data-stu-id="3039f-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>  
  
 <span data-ttu-id="3039f-104">Beim Hinzufügen von <xref:System.Windows.Forms.ToolStripItem>s, die mehr Platz benötigen, als zu erfordern die <xref:System.Windows.Forms.ToolStrip> aktuelle Größe des Formulars, ein <xref:System.Windows.Forms.ToolStripOverflowButton> automatisch angezeigt, auf die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="3039f-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="3039f-105">Die <xref:System.Windows.Forms.ToolStripOverflowButton> angezeigt wird, und die Overflow-fähige Elemente in der Dropdown-Überlaufmenü verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="3039f-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="3039f-106">Dadurch können Sie anpassen und priorisieren wie Ihre <xref:System.Windows.Forms.ToolStrip> Elemente ordnungsgemäß angepasst werden, um unterschiedliche Formulargrößen.</span><span class="sxs-lookup"><span data-stu-id="3039f-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="3039f-107">Sie können auch die Darstellung der Elemente ändern, wenn sie in der Überlaufspalte mithilfe fallen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> und <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> Eigenschaften und die <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3039f-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="3039f-108">Wenn Sie das Formular zur Entwurfszeit oder zur Laufzeit mehr vergrößern, <xref:System.Windows.Forms.ToolStripItem>s angezeigt werden kann, klicken Sie im hauptblatt <xref:System.Windows.Forms.ToolStrip> und die <xref:System.Windows.Forms.ToolStripOverflowButton> möglicherweise ausgeblendet, bis Sie die Größe des Formulars zu verringern.</span><span class="sxs-lookup"><span data-stu-id="3039f-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="3039f-109">So aktivieren Sie einen Überlauf in einem ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3039f-109">To enable overflow on a ToolStrip control</span></span>  
  
-   <span data-ttu-id="3039f-110">Sicherstellen, dass die <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> Eigenschaft nicht festgelegt ist, um `false` für die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="3039f-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="3039f-111">Die Standardeinstellung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="3039f-111">The default is `True`.</span></span>  
  
     <span data-ttu-id="3039f-112">Beim <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> ist `True` (Standard), eine <xref:System.Windows.Forms.ToolStripItem> wird gesendet, um die Dropdownliste Überlaufmenü bei den Inhalt des der <xref:System.Windows.Forms.ToolStripItem> überschreitet die Breite einer horizontalen <xref:System.Windows.Forms.ToolStrip> oder die Höhe eines vertikalen <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="3039f-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="3039f-113">Überlaufverhalten eines bestimmten ToolStripItem angeben</span><span class="sxs-lookup"><span data-stu-id="3039f-113">To specify overflow behavior of a specific ToolStripItem</span></span>  
  
-   <span data-ttu-id="3039f-114">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> Eigenschaft von der <xref:System.Windows.Forms.ToolStripItem> auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="3039f-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="3039f-115">Mögliche Werte sind `Always`, `Never`, und `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="3039f-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="3039f-116">Die Defaultis `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="3039f-116">The defaultis `AsNeeded`.</span></span>  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3039f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3039f-117">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="3039f-118">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3039f-118">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="3039f-119">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="3039f-119">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="3039f-120">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="3039f-120">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
