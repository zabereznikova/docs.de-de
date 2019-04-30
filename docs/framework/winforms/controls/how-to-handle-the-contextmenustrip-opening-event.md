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
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941296"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="eca4a-102">Vorgehensweise: Behandeln des Opening-Ereignisses von ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="eca4a-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="eca4a-103">Sie können das Verhalten anpassen Ihrer <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelements durch Behandeln der <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="eca4a-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eca4a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eca4a-104">Example</span></span>  
 <span data-ttu-id="eca4a-105">Im folgenden Codebeispiel wird veranschaulicht, wie behandelt die <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="eca4a-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="eca4a-106">Der Ereignishandler fügt Elemente dynamisch zu einem <xref:System.Windows.Forms.ContextMenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eca4a-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="eca4a-107">Das vollständige Codebeispiel finden Sie unter [Vorgehensweise: Dynamisches Hinzufügen von ToolStrip-Elementen](how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="eca4a-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="eca4a-108">Legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> Eigenschaft `true` um zu verhindern, dass Sie im Menü öffnen.</span><span class="sxs-lookup"><span data-stu-id="eca4a-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca4a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eca4a-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="eca4a-110">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="eca4a-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
