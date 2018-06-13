---
title: 'Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: acf5967c015d61a0cc148e5cb509a5a7ded2152c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533197"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="2600b-102">Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="2600b-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="2600b-103">Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>-Steuerelements anpassen, indem Sie eine von <xref:System.Windows.Forms.ToolStripRenderer> abgeleitete Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="2600b-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="2600b-104">Damit verfügen Sie über die Flexibilität zum Erstellen einer Darstellung, die sich von der von den Klassen <xref:System.Windows.Forms.ToolStripProfessionalRenderer> und <xref:System.Windows.Forms.ToolStripSystemRenderer> bereitgestellten unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2600b-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2600b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2600b-105">Example</span></span>  
 <span data-ttu-id="2600b-106">Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Windows.Forms.ToolStripRenderer>-Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2600b-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="2600b-107">In diesem Beispiel implementiert das `GridStrip`-Steuerelement ein Puzzle mit gleitenden Kacheln, das es dem Benutzer ermöglicht, die Kacheln in einem Tabellenlayout zu verschieben, um ein Bild zusammenzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2600b-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="2600b-108">Ein benutzerdefiniertes <xref:System.Windows.Forms.ToolStrip>-Steuerelement ordnet seine <xref:System.Windows.Forms.ToolStripButton>-Steuerelemente in einem Rasterlayout an.</span><span class="sxs-lookup"><span data-stu-id="2600b-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="2600b-109">Das Layout enthält eine leere Zelle, in die der Benutzer per Drag&Drop eine benachbarte Kachel ziehen kann.</span><span class="sxs-lookup"><span data-stu-id="2600b-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="2600b-110">Kacheln, die vom Benutzer verschoben werden können, sind hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="2600b-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="2600b-111">Mit der `GridStripRenderer`-Klasse werden drei Aspekte der Darstellung des `GridStrip`-Steuerelements angepasst:</span><span class="sxs-lookup"><span data-stu-id="2600b-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="2600b-112">`GridStrip`-Rahmen</span><span class="sxs-lookup"><span data-stu-id="2600b-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="2600b-113"><xref:System.Windows.Forms.ToolStripButton>-Rahmen</span><span class="sxs-lookup"><span data-stu-id="2600b-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="2600b-114"><xref:System.Windows.Forms.ToolStripButton>-Bild</span><span class="sxs-lookup"><span data-stu-id="2600b-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2600b-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2600b-115">Compiling the Code</span></span>  
 <span data-ttu-id="2600b-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2600b-116">This example requires:</span></span>  
  
-   <span data-ttu-id="2600b-117">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="2600b-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2600b-118">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2600b-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2600b-119">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="2600b-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="2600b-120">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2600b-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2600b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2600b-121">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="2600b-122">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2600b-122">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
