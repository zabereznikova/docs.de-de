---
title: 'Gewusst wie: Festlegen des ToolStrip-Renderers zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 98a027cb8cd913e3e2d00db16fc2f527159a1c87
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46472294"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="94fd2-102">Gewusst wie: Festlegen des ToolStrip-Renderers zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="94fd2-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="94fd2-103">Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>-Steuerelements anpassen, indem Sie eine benutzerdefinierte `ProfessionalColorTable`-Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="94fd2-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94fd2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94fd2-104">Example</span></span>  
 <span data-ttu-id="94fd2-105">Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte `ProfessionalColorTable`-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94fd2-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="94fd2-106">Diese Klasse definiert Farbverläufe für ein <xref:System.Windows.Forms.MenuStrip>- und ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="94fd2-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="94fd2-107">Um dieses Codebeispiel zu verwenden, kompilieren Sie die Anwendung, führen Sie die Anwendung aus, und klicken Sie dann auf **Change Colors** (Farben ändern), um die Farbverläufe anzuwenden, die in der benutzerdefinierten `ProfessionalColorTable`-Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="94fd2-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="94fd2-108">Definieren einer benutzerdefinierten ProfessionalColorTable-Klasse</span><span class="sxs-lookup"><span data-stu-id="94fd2-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="94fd2-109">Die benutzerdefinierten Farbverläufe sind in der `CustomProfessionalColors`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="94fd2-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="94fd2-110">Zuweisen eines benutzerdefinierten Renderers</span><span class="sxs-lookup"><span data-stu-id="94fd2-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="94fd2-111">Erstellen Sie eine neue `ToolStripProfessionalRenderer`-Instanz mit der `CustomProfessionalColors`-Klasse, und weisen Sie diese Instanz der <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>-Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="94fd2-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94fd2-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="94fd2-112">Compiling the Code</span></span>  
 <span data-ttu-id="94fd2-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="94fd2-113">This example requires:</span></span>  
  
-   <span data-ttu-id="94fd2-114">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="94fd2-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="94fd2-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="94fd2-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="94fd2-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="94fd2-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="94fd2-117">Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="94fd2-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fd2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94fd2-118">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.ProfessionalColorTable>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [<span data-ttu-id="94fd2-119">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="94fd2-119">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
