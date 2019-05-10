---
title: 'Vorgehensweise: Implementieren eines benutzerdefinierten ToolStripRenderer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: ec74528ecb3d2ca1fca78c3a81e71a0093843b4d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651662"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="73288-102">Vorgehensweise: Implementieren eines benutzerdefinierten ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="73288-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="73288-103">Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>-Steuerelements anpassen, indem Sie eine von <xref:System.Windows.Forms.ToolStripRenderer> abgeleitete Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="73288-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="73288-104">Damit verfügen Sie über die Flexibilität zum Erstellen einer Darstellung, die sich von der von den Klassen <xref:System.Windows.Forms.ToolStripProfessionalRenderer> und <xref:System.Windows.Forms.ToolStripSystemRenderer> bereitgestellten unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="73288-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73288-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73288-105">Example</span></span>  
 <span data-ttu-id="73288-106">Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Windows.Forms.ToolStripRenderer>-Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="73288-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="73288-107">In diesem Beispiel implementiert das `GridStrip`-Steuerelement ein Puzzle mit gleitenden Kacheln, das es dem Benutzer ermöglicht, die Kacheln in einem Tabellenlayout zu verschieben, um ein Bild zusammenzusetzen.</span><span class="sxs-lookup"><span data-stu-id="73288-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="73288-108">Ein benutzerdefiniertes <xref:System.Windows.Forms.ToolStrip>-Steuerelement ordnet seine <xref:System.Windows.Forms.ToolStripButton>-Steuerelemente in einem Rasterlayout an.</span><span class="sxs-lookup"><span data-stu-id="73288-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="73288-109">Das Layout enthält eine leere Zelle, in die der Benutzer per Drag&Drop eine benachbarte Kachel ziehen kann.</span><span class="sxs-lookup"><span data-stu-id="73288-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="73288-110">Kacheln, die vom Benutzer verschoben werden können, sind hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="73288-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="73288-111">Mit der `GridStripRenderer`-Klasse werden drei Aspekte der Darstellung des `GridStrip`-Steuerelements angepasst:</span><span class="sxs-lookup"><span data-stu-id="73288-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="73288-112">`GridStrip`-Rahmen</span><span class="sxs-lookup"><span data-stu-id="73288-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="73288-113"><xref:System.Windows.Forms.ToolStripButton>-Rahmen</span><span class="sxs-lookup"><span data-stu-id="73288-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="73288-114"><xref:System.Windows.Forms.ToolStripButton>-Bild</span><span class="sxs-lookup"><span data-stu-id="73288-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73288-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="73288-115">Compiling the Code</span></span>  
 <span data-ttu-id="73288-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="73288-116">This example requires:</span></span>  
  
- <span data-ttu-id="73288-117">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="73288-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="73288-118">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="73288-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="73288-119">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="73288-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73288-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73288-120">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="73288-121">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="73288-121">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
