---
title: 'Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 1e6455ebabfa5b27301f98b89861348b28d415af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690201"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="563a9-102">Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="563a9-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="563a9-103">Sie können den <xref:System.Windows.Forms.ToolStrip>-Steuerelementen Ihrer Anwendung ein professionelles Aussehen und Verhalten ("Look and Feel") verleihen, indem Sie eine eigene Klasse schreiben, die vom Typ <xref:System.Windows.Forms.ToolStripProfessionalRenderer> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="563a9-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="563a9-104">Bietet umfassende Unterstützung für dieses Feature in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="563a9-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="563a9-105">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="563a9-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="563a9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="563a9-106">Example</span></span>  
 <span data-ttu-id="563a9-107">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente ein zusammengesetztes Steuerelements zu erstellen, die imitiert die **Navigationsbereich** von Microsoft® Outlook® bereitgestellten.</span><span class="sxs-lookup"><span data-stu-id="563a9-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="563a9-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="563a9-108">Compiling the Code</span></span>  
 <span data-ttu-id="563a9-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="563a9-109">This example requires:</span></span>  
  
-   <span data-ttu-id="563a9-110">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="563a9-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="563a9-111">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="563a9-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="563a9-112">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="563a9-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="563a9-113">Siehe auch [Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="563a9-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="563a9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="563a9-114">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="563a9-115">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="563a9-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [<span data-ttu-id="563a9-116">Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="563a9-116">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
