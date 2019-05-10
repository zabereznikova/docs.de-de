---
title: 'Vorgehensweise: Konfigurieren des Aktivierungs- und Bildrands von MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 5db4b3546b6c15af916d53b1a53c347174f1f30b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643127"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="061cf-102">Vorgehensweise: Konfigurieren des Aktivierungs- und Bildrands von MenuStrip</span><span class="sxs-lookup"><span data-stu-id="061cf-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="061cf-103">Sie können eine <xref:System.Windows.Forms.MenuStrip>-Instanz anpassen, indem Sie die <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A>- und die <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A>-Eigenschaft in verschiedenen Kombinationen festlegen.</span><span class="sxs-lookup"><span data-stu-id="061cf-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="061cf-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="061cf-104">Example</span></span>  
 <span data-ttu-id="061cf-105">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.ContextMenuStrip>-Aktivierungs-und -Bildränder festgelegt und angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="061cf-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="061cf-106">Die Vorgehensweise ist für eine <xref:System.Windows.Forms.ContextMenuStrip>- oder eine <xref:System.Windows.Forms.MenuStrip>-Instanz identisch.</span><span class="sxs-lookup"><span data-stu-id="061cf-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="061cf-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="061cf-107">Compiling the Code</span></span>  
 <span data-ttu-id="061cf-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="061cf-108">This example requires:</span></span>  
  
- <span data-ttu-id="061cf-109">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="061cf-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="061cf-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="061cf-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="061cf-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="061cf-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="061cf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="061cf-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="061cf-113">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="061cf-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="061cf-114">Vorgehensweise: Aktivieren des Aktivierungs- und Bildrands in ContextMenuStrip-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="061cf-114">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
