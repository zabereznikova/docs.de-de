---
title: 'Vorgehensweise: Erstellen eines MDI-Formulars mit ToolStripPanel-Steuerelementen'
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
ms.openlocfilehash: 55c2294496800fb8692d3c8215c1c13f7dac9b01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746961"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="b00b4-102">Vorgehensweise: Erstellen eines MDI-Formulars mit ToolStripPanel-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b00b4-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="b00b4-103">Sie können ein Formular mit einer mehrfachen Dokumentschnittstelle (MDI) erstellen, das mit <xref:System.Windows.Forms.ToolStrip>-Steuerelementen auf allen vier Seiten umrahmt wird.</span><span class="sxs-lookup"><span data-stu-id="b00b4-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b00b4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b00b4-104">Example</span></span>  
 <span data-ttu-id="b00b4-105">Im folgenden Codebeispiel wird gezeigt, wie Sie angedockte <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente verwenden, um ein MDI-Fenster mit vier <xref:System.Windows.Forms.ToolStrip>-Steuerelementen einzurahmen.</span><span class="sxs-lookup"><span data-stu-id="b00b4-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="b00b4-106">In diesem Beispiel fügt die <xref:System.Windows.Forms.ToolStripPanel.Join%2A>-Methode die <xref:System.Windows.Forms.ToolStrip>-Steuerelemente an die entsprechenden <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente an.</span><span class="sxs-lookup"><span data-stu-id="b00b4-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b00b4-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b00b4-107">Compiling the Code</span></span>  
 <span data-ttu-id="b00b4-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b00b4-108">This example requires:</span></span>  
  
- <span data-ttu-id="b00b4-109">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="b00b4-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b00b4-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b00b4-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b00b4-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="b00b4-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00b4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b00b4-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="b00b4-113">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b00b4-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
