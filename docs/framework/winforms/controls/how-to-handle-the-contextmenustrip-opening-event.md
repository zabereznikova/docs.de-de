---
title: 'Gewusst wie: Behandeln des Opening-Ereignisses von ContextMenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: c5af03f4726063754f81ec9226b4b161599b4121
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531861"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="5b618-102">Gewusst wie: Behandeln des Opening-Ereignisses von ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5b618-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="5b618-103">Sie können das Verhalten anpassen Ihrer <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelements durch Behandeln der <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5b618-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b618-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b618-104">Example</span></span>  
 <span data-ttu-id="5b618-105">Im folgenden Codebeispiel wird veranschaulicht, wie behandelt die <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5b618-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="5b618-106">Der Ereignishandler fügt Elemente dynamisch zu einem <xref:System.Windows.Forms.ContextMenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5b618-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="5b618-107">Das vollständige Codebeispiel finden Sie unter [wie: Hinzufügen ToolStrip-Elemente dynamisch](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="5b618-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="5b618-108">Festlegen der <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> Eigenschaft `true` , öffnen Sie im Menü verhindern.</span><span class="sxs-lookup"><span data-stu-id="5b618-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b618-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b618-109">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="5b618-110">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5b618-110">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
