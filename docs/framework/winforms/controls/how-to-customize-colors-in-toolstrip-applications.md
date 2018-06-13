---
title: 'Gewusst wie: Anpassen von Farben in ToolStrip-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 50e1fcbea053737216849eb966a2e28d19a3f529
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530392"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="c84c1-102">Gewusst wie: Anpassen von Farben in ToolStrip-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="c84c1-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="c84c1-103">Sie können die Darstellung von <xref:System.Windows.Forms.ToolStrip> mithilfe der <xref:System.Windows.Forms.ToolStripProfessionalRenderer>-Klasse anpassen, um benutzerdefinierte Farben zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c84c1-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84c1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c84c1-104">Example</span></span>  
 <span data-ttu-id="c84c1-105">Das folgende Codebeispiel zeigt, wie Sie <xref:System.Windows.Forms.ToolStripProfessionalRenderer> zum Definieren benutzerdefinierter Farben zur Laufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="c84c1-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c84c1-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c84c1-106">Compiling the Code</span></span>  
 <span data-ttu-id="c84c1-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c84c1-107">This example requires:</span></span>  
  
-   <span data-ttu-id="c84c1-108">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="c84c1-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c84c1-109">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c84c1-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c84c1-110">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="c84c1-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c84c1-111">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c84c1-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84c1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c84c1-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.ProfessionalColorTable>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
