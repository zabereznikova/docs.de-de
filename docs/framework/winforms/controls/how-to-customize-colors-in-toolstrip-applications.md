---
title: 'Vorgehensweise: Anpassen von Farben in ToolStrip-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 4d051085bdba41b9784d3dd7f921189c1300daf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052975"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="893de-102">Vorgehensweise: Anpassen von Farben in ToolStrip-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="893de-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="893de-103">Sie können die Darstellung von <xref:System.Windows.Forms.ToolStrip> mithilfe der <xref:System.Windows.Forms.ToolStripProfessionalRenderer>-Klasse anpassen, um benutzerdefinierte Farben zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="893de-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="893de-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="893de-104">Example</span></span>  
 <span data-ttu-id="893de-105">Das folgende Codebeispiel zeigt, wie Sie <xref:System.Windows.Forms.ToolStripProfessionalRenderer> zum Definieren benutzerdefinierter Farben zur Laufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="893de-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="893de-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="893de-106">Compiling the Code</span></span>  
 <span data-ttu-id="893de-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="893de-107">This example requires:</span></span>  
  
- <span data-ttu-id="893de-108">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="893de-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="893de-109">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="893de-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="893de-110">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="893de-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893de-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="893de-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
