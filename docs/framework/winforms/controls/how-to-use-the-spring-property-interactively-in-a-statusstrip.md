---
title: 'Vorgehensweise: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 8750c48d08161260a1dba6ab69098980f25a5d55
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589650"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="ce677-102">Vorgehensweise: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ce677-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="ce677-103">Sie können die Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> verwenden, um ein <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement in einem <xref:System.Windows.Forms.StatusStrip>-Steuerelement zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="ce677-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="ce677-104">Die Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> bestimmt, ob das <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement den verfügbaren Platz für das <xref:System.Windows.Forms.StatusStrip>-Steuerelement ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="ce677-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce677-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce677-105">Example</span></span>  
 <span data-ttu-id="ce677-106">Im folgenden Codebeispiel wird veranschaulicht, wie die Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> zum Positionieren eines <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelements in einem <xref:System.Windows.Forms.StatusStrip>-Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce677-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="ce677-107">Der <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignishandler führt einen exklusiven oder Oder-Vorgang (XOR) aus, um den Wert der Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ce677-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="ce677-108">Um dieses Codebeispiel zu verwenden, kompilieren und Ausführen der Anwendung, und klicken Sie dann auf **Middle (Spring)** auf die <xref:System.Windows.Forms.StatusStrip> Steuerelement, das den Wert der wechseln die <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ce677-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ce677-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ce677-109">Compiling the Code</span></span>  
 <span data-ttu-id="ce677-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ce677-110">This example requires:</span></span>  
  
- <span data-ttu-id="ce677-111">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="ce677-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce677-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce677-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="ce677-113">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ce677-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
