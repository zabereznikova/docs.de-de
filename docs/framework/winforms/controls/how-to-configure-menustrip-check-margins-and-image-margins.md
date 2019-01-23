---
title: 'Vorgehensweise: MenuStrip konfigurieren Aktivierungs- und Bildrands'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 49c228fef387a7c2a18cf8cecd5081e7b5519ab3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530774"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="81e93-102">Vorgehensweise: MenuStrip konfigurieren Aktivierungs- und Bildrands</span><span class="sxs-lookup"><span data-stu-id="81e93-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="81e93-103">Sie können eine <xref:System.Windows.Forms.MenuStrip>-Instanz anpassen, indem Sie die <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A>- und die <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A>-Eigenschaft in verschiedenen Kombinationen festlegen.</span><span class="sxs-lookup"><span data-stu-id="81e93-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81e93-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81e93-104">Example</span></span>  
 <span data-ttu-id="81e93-105">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.ContextMenuStrip>-Aktivierungs-und -Bildränder festgelegt und angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="81e93-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="81e93-106">Die Vorgehensweise ist für eine <xref:System.Windows.Forms.ContextMenuStrip>- oder eine <xref:System.Windows.Forms.MenuStrip>-Instanz identisch.</span><span class="sxs-lookup"><span data-stu-id="81e93-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81e93-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="81e93-107">Compiling the Code</span></span>  
 <span data-ttu-id="81e93-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="81e93-108">This example requires:</span></span>  
  
-   <span data-ttu-id="81e93-109">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="81e93-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="81e93-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="81e93-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="81e93-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="81e93-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="81e93-112">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="81e93-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e93-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81e93-113">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="81e93-114">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="81e93-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [<span data-ttu-id="81e93-115">Vorgehensweise: Aktivieren des Aktivierungs- und Bildrands in ContextMenuStrip-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="81e93-115">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
