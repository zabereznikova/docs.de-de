---
title: 'Vorgehensweise: Behandeln des Opening-Ereignisses von ContextMenuStrip'
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
ms.openlocfilehash: 179411da96362fd9ba42e2b97682f335beb894c1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715450"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="1a20b-102">Vorgehensweise: Behandeln des Opening-Ereignisses von ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="1a20b-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="1a20b-103">Sie können das Verhalten anpassen Ihrer <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelements durch Behandeln der <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1a20b-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a20b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a20b-104">Example</span></span>  
 <span data-ttu-id="1a20b-105">Im folgenden Codebeispiel wird veranschaulicht, wie behandelt die <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1a20b-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="1a20b-106">Der Ereignishandler fügt Elemente dynamisch zu einem <xref:System.Windows.Forms.ContextMenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1a20b-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="1a20b-107">Das vollständige Codebeispiel finden Sie unter [Vorgehensweise: Dynamisches Hinzufügen von ToolStrip-Elementen](how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="1a20b-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="1a20b-108">Legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> Eigenschaft `true` um zu verhindern, dass Sie im Menü öffnen.</span><span class="sxs-lookup"><span data-stu-id="1a20b-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a20b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a20b-109">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="1a20b-110">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1a20b-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
