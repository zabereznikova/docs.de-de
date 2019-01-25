---
title: 'Vorgehensweise: Aktivieren Sie die TAB-Taste zum Verlassen eines ToolStrip-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: a98c8a54389daa898c877a08f8cc2cae46a11da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663070"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="797db-102">Vorgehensweise: Aktivieren Sie die TAB-Taste zum Verlassen eines ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="797db-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="797db-103">Verwenden Sie das folgende Verfahren, um dem Benutzer ermöglichen, die TAB-Taste zum Verschieben von einer <xref:System.Windows.Forms.ToolStrip> auf das nächste Steuerelement in der Aktivierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="797db-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="797db-104">Die <xref:System.Windows.Forms.ToolStrip> akzeptiert das erste Drücken der TAB-Taste und der Pfeil Schlüssel wählen Elemente in der <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="797db-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="797db-105">Wenn der Benutzer ein zweites Mal die TAB-Taste drückt, dauert es den Benutzer das nächste Steuerelement in der Aktivierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="797db-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="797db-106">Um dem Benutzer die TAB-Taste zum Verlassen eines ToolStrip zum nächsten Steuerelement zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="797db-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="797db-107">Legen Sie die <xref:System.Windows.Forms.ToolStrip.TabStop%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStrip> zu `true`.</span><span class="sxs-lookup"><span data-stu-id="797db-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797db-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="797db-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="797db-109">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="797db-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
