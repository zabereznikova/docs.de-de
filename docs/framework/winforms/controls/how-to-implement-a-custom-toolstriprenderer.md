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
ms.openlocfilehash: 4a84571bf8b81cd26c864edcd4d313a4009dda16
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592428"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="477a0-102">Vorgehensweise: Implementieren eines benutzerdefinierten ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="477a0-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="477a0-103">Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>-Steuerelements anpassen, indem Sie eine von <xref:System.Windows.Forms.ToolStripRenderer> abgeleitete Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="477a0-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="477a0-104">Damit verfügen Sie über die Flexibilität zum Erstellen einer Darstellung, die sich von der von den Klassen <xref:System.Windows.Forms.ToolStripProfessionalRenderer> und <xref:System.Windows.Forms.ToolStripSystemRenderer> bereitgestellten unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="477a0-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="477a0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="477a0-105">Example</span></span>  
 <span data-ttu-id="477a0-106">Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Windows.Forms.ToolStripRenderer>-Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="477a0-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="477a0-107">In diesem Beispiel implementiert das `GridStrip`-Steuerelement ein Puzzle mit gleitenden Kacheln, das es dem Benutzer ermöglicht, die Kacheln in einem Tabellenlayout zu verschieben, um ein Bild zusammenzusetzen.</span><span class="sxs-lookup"><span data-stu-id="477a0-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="477a0-108">Ein benutzerdefiniertes <xref:System.Windows.Forms.ToolStrip>-Steuerelement ordnet seine <xref:System.Windows.Forms.ToolStripButton>-Steuerelemente in einem Rasterlayout an.</span><span class="sxs-lookup"><span data-stu-id="477a0-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="477a0-109">Das Layout enthält eine leere Zelle, in die der Benutzer per Drag&Drop eine benachbarte Kachel ziehen kann.</span><span class="sxs-lookup"><span data-stu-id="477a0-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="477a0-110">Kacheln, die vom Benutzer verschoben werden können, sind hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="477a0-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="477a0-111">Mit der `GridStripRenderer`-Klasse werden drei Aspekte der Darstellung des `GridStrip`-Steuerelements angepasst:</span><span class="sxs-lookup"><span data-stu-id="477a0-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="477a0-112">`GridStrip`-Rahmen</span><span class="sxs-lookup"><span data-stu-id="477a0-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="477a0-113"><xref:System.Windows.Forms.ToolStripButton>-Rahmen</span><span class="sxs-lookup"><span data-stu-id="477a0-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="477a0-114"><xref:System.Windows.Forms.ToolStripButton>-Bild</span><span class="sxs-lookup"><span data-stu-id="477a0-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="477a0-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="477a0-115">Compiling the Code</span></span>  
 <span data-ttu-id="477a0-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="477a0-116">This example requires:</span></span>  
  
- <span data-ttu-id="477a0-117">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="477a0-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477a0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="477a0-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="477a0-119">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="477a0-119">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
