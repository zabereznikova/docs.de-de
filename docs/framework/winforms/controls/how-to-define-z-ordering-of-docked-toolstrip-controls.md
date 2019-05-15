---
title: 'Vorgehensweise: Definieren der Z-Reihenfolge angedockter ToolStrip-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 514c9dd1c91adcadf6f5d383ba734886dec3151d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591906"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="a51aa-102">Vorgehensweise: Definieren der Z-Reihenfolge angedockter ToolStrip-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a51aa-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="a51aa-103">Damit ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement ordnungsgemäß angedockt wird, müssen Sie das Steuerelement ordnungsgemäß in der Z-Reihenfolge des Formulars positionieren.</span><span class="sxs-lookup"><span data-stu-id="a51aa-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a51aa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a51aa-104">Example</span></span>  
 <span data-ttu-id="a51aa-105">Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement und ein angedocktes <xref:System.Windows.Forms.MenuStrip>-Steuerelement durch Angabe der Z-Reihenfolge angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a51aa-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="a51aa-106">Die Z-Reihenfolge wird durch die Reihenfolge bestimmt, in der das <xref:System.Windows.Forms.ToolStrip>-Steuerelement und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a51aa-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="a51aa-107">der <xref:System.Windows.Forms.Control.Controls%2A>-Auflistung des Formulars hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a51aa-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="a51aa-108">Kehren Sie die Reihenfolge dieser Aufrufe der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>-Methode um, und beobachten Sie die Auswirkung auf das Layout.</span><span class="sxs-lookup"><span data-stu-id="a51aa-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a51aa-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a51aa-109">Compiling the Code</span></span>  
 <span data-ttu-id="a51aa-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a51aa-110">This example requires:</span></span>  
  
- <span data-ttu-id="a51aa-111">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="a51aa-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51aa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a51aa-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>
- <xref:System.Windows.Forms.Control.Controls%2A>
- <xref:System.Windows.Forms.Control.Dock%2A>
- [<span data-ttu-id="a51aa-113">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a51aa-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
