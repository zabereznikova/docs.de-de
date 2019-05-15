---
title: 'Vorgehensweise: Ausrichten von gezeichnetem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 3a569284a1c4b43fa7264e0354934436f95b8dc3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589381"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="8b20b-102">Vorgehensweise: Ausrichten von gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="8b20b-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="8b20b-103">Wenn Sie eine benutzerdefinierte Zeichnung durchführen, sollten Sie häufig gezeichnetem Text in einem Formular oder Steuerelement zu zentrieren.</span><span class="sxs-lookup"><span data-stu-id="8b20b-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="8b20b-104">Sie können problemlos mit gezeichneter Text Ausrichten der <xref:System.Drawing.Graphics.DrawString%2A> oder <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden, mit der richtigen Formatierungsobjekt erstellen und Festlegen von Flags für die Kultur spezifische Format.</span><span class="sxs-lookup"><span data-stu-id="8b20b-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="8b20b-105">So zeichnen Sie zentrierten Text mit GDI + ("DrawString")</span><span class="sxs-lookup"><span data-stu-id="8b20b-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1. <span data-ttu-id="8b20b-106">Verwenden einer <xref:System.Drawing.StringFormat> mit dem entsprechenden <xref:System.Drawing.Graphics.DrawString%2A> Methode, um zentriert Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b20b-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="8b20b-107">So zeichnen Sie zentrierten Text mit GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="8b20b-107">To draw centered text with GDI (DrawText)</span></span>  
  
1. <span data-ttu-id="8b20b-108">Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumeration für wrapping als auch vertikal und horizontal zentrieren Text mit der entsprechenden <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8b20b-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8b20b-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8b20b-109">Compiling the Code</span></span>  
 <span data-ttu-id="8b20b-110">Die vorherigen Codebeispiele für den Einsatz mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8b20b-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b20b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b20b-111">See also</span></span>

- [<span data-ttu-id="8b20b-112">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="8b20b-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="8b20b-113">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="8b20b-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="8b20b-114">Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="8b20b-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
