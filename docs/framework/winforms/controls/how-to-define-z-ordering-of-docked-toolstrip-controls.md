---
title: 'Gewusst wie: Definieren der Z-Reihenfolge angedockter ToolStrip-Steuerelemente'
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
ms.openlocfilehash: 34d600454a7fa63c7ba59bebded6365cd5401cb4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064737"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="86d91-102">Gewusst wie: Definieren der Z-Reihenfolge angedockter ToolStrip-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="86d91-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="86d91-103">Damit ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement ordnungsgemäß angedockt wird, müssen Sie das Steuerelement ordnungsgemäß in der Z-Reihenfolge des Formulars positionieren.</span><span class="sxs-lookup"><span data-stu-id="86d91-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d91-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86d91-104">Example</span></span>  
 <span data-ttu-id="86d91-105">Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement und ein angedocktes <xref:System.Windows.Forms.MenuStrip>-Steuerelement durch Angabe der Z-Reihenfolge angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86d91-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="86d91-106">Die Z-Reihenfolge wird durch die Reihenfolge bestimmt, in der das <xref:System.Windows.Forms.ToolStrip>-Steuerelement und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="86d91-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="86d91-107">der <xref:System.Windows.Forms.Control.Controls%2A>-Auflistung des Formulars hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="86d91-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="86d91-108">Kehren Sie die Reihenfolge dieser Aufrufe der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>-Methode um, und beobachten Sie die Auswirkung auf das Layout.</span><span class="sxs-lookup"><span data-stu-id="86d91-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86d91-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="86d91-109">Compiling the Code</span></span>  
 <span data-ttu-id="86d91-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="86d91-110">This example requires:</span></span>  
  
-   <span data-ttu-id="86d91-111">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="86d91-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="86d91-112">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="86d91-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="86d91-113">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="86d91-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="86d91-114">Siehe auch [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="86d91-114">Also se [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d91-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86d91-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [<span data-ttu-id="86d91-116">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="86d91-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
