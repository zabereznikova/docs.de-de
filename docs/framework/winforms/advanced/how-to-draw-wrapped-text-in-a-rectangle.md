---
title: 'Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524972"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="e93d0-102">Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck</span><span class="sxs-lookup"><span data-stu-id="e93d0-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="e93d0-103">Umbrochenen Text können in einem Rechteck gezeichnet werden, mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, der die <xref:System.Drawing.Graphics> -Klasse, akzeptiert eine <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF> Parameter.</span><span class="sxs-lookup"><span data-stu-id="e93d0-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="e93d0-104">Verwenden Sie ebenfalls eine <xref:System.Drawing.Brush> und ein <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="e93d0-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="e93d0-105">Sie können auch umbrochenen Text in einem Rechteck zeichnen, mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladenen Methode des der <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Rectangle> und eine <xref:System.Windows.Forms.TextFormatFlags> Parameter.</span><span class="sxs-lookup"><span data-stu-id="e93d0-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="e93d0-106">Verwenden Sie ebenfalls eine <xref:System.Drawing.Color> und ein <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="e93d0-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="e93d0-107">Die folgende Abbildung zeigt die Ausgabe von Text in das Rechteck gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="e93d0-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="e93d0-108">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="e93d0-108">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="e93d0-109">Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI +</span><span class="sxs-lookup"><span data-stu-id="e93d0-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="e93d0-110">Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, und übergeben Sie den gewünschten Text <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> und <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="e93d0-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="e93d0-111">Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI</span><span class="sxs-lookup"><span data-stu-id="e93d0-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="e93d0-112">Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumerationswert an den Text eingebunden werden soll, mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, und übergeben Sie den gewünschten Text <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> und <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="e93d0-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e93d0-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e93d0-113">Compiling the Code</span></span>  
 <span data-ttu-id="e93d0-114">Die vorherigen Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e93d0-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="e93d0-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="e93d0-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93d0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e93d0-116">See Also</span></span>  
 [<span data-ttu-id="e93d0-117">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="e93d0-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="e93d0-118">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="e93d0-118">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="e93d0-119">Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="e93d0-119">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="e93d0-120">Gewusst wie: Zeichnen von Text an einer angegebenen Position</span><span class="sxs-lookup"><span data-stu-id="e93d0-120">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
