---
title: 'Gewusst wie: Ausrichten von gezeichnetem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 96e14ef510a08ed0c387733e37b6acae6cbd31cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522756"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="71a3a-102">Gewusst wie: Ausrichten von gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="71a3a-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="71a3a-103">Wenn Sie benutzerdefinierte Zeichnung zu erstellen, möchten Sie möglicherweise häufig gezeichnetem Text in einem Formular oder Steuerelement zu zentrieren.</span><span class="sxs-lookup"><span data-stu-id="71a3a-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="71a3a-104">Sie können problemlos mit gezeichneter Text Ausrichten der <xref:System.Drawing.Graphics.DrawString%2A> oder <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden durch die richtige Formatierungsobjekt erstellen und die Kultur spezifische Formatflags festlegen.</span><span class="sxs-lookup"><span data-stu-id="71a3a-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="71a3a-105">So zeichnen Sie zentrierten Text mit GDI + (DrawString)</span><span class="sxs-lookup"><span data-stu-id="71a3a-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="71a3a-106">Verwenden einer <xref:System.Drawing.StringFormat> mit dem entsprechenden <xref:System.Drawing.Graphics.DrawString%2A> Methode, um zentriert Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="71a3a-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="71a3a-107">So zeichnen Sie zentrierten Text mit GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="71a3a-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="71a3a-108">Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumeration für wrapping als auch vertikal und horizontal zentrieren von Text mit dem entsprechenden <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="71a3a-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71a3a-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="71a3a-109">Compiling the Code</span></span>  
 <span data-ttu-id="71a3a-110">Die vorherigen Codebeispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="71a3a-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a3a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71a3a-111">See Also</span></span>  
 [<span data-ttu-id="71a3a-112">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="71a3a-112">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="71a3a-113">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="71a3a-113">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="71a3a-114">Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="71a3a-114">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
