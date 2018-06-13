---
title: 'Gewusst wie: Erstellen eines MDI-Formulars mit ToolStripPanel-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 1f7da5bfea9a9864f11a32a589798dfd8a7844a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530454"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="7b071-102">Gewusst wie: Erstellen eines MDI-Formulars mit ToolStripPanel-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7b071-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="7b071-103">Sie können ein Formular mit einer mehrfachen Dokumentschnittstelle (MDI) erstellen, das mit <xref:System.Windows.Forms.ToolStrip>-Steuerelementen auf allen vier Seiten umrahmt wird.</span><span class="sxs-lookup"><span data-stu-id="7b071-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b071-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b071-104">Example</span></span>  
 <span data-ttu-id="7b071-105">Im folgenden Codebeispiel wird gezeigt, wie Sie angedockte <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente verwenden, um ein MDI-Fenster mit vier <xref:System.Windows.Forms.ToolStrip>-Steuerelementen einzurahmen.</span><span class="sxs-lookup"><span data-stu-id="7b071-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="7b071-106">In diesem Beispiel fügt die <xref:System.Windows.Forms.ToolStripPanel.Join%2A>-Methode die <xref:System.Windows.Forms.ToolStrip>-Steuerelemente an die entsprechenden <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente an.</span><span class="sxs-lookup"><span data-stu-id="7b071-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b071-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7b071-107">Compiling the Code</span></span>  
 <span data-ttu-id="7b071-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7b071-108">This example requires:</span></span>  
  
-   <span data-ttu-id="7b071-109">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="7b071-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7b071-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7b071-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7b071-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="7b071-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="7b071-112">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="7b071-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b071-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b071-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 <xref:System.Windows.Forms.ToolStripPanel.Join%2A>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="7b071-114">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7b071-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
