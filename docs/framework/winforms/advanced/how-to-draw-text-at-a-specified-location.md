---
title: 'Vorgehensweise: Zeichnen von Text an einer angegebenen Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 3f54da182e6cc1489eadba6fa1d3cef683c3ba51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075508"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="07985-102">Vorgehensweise: Zeichnen von Text an einer angegebenen Position</span><span class="sxs-lookup"><span data-stu-id="07985-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="07985-103">Wenn Sie eine benutzerdefinierte Zeichnung durchführen, können Sie Text in einer einzigen Zeile ab, zu einem bestimmten Zeitpunkt zeichnen.</span><span class="sxs-lookup"><span data-stu-id="07985-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="07985-104">Sie können auf diese Weise Text zeichnen, mit der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, die von der <xref:System.Drawing.Graphics> -Klasse, akzeptiert eine <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF> Parameter.</span><span class="sxs-lookup"><span data-stu-id="07985-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="07985-105">Die <xref:System.Drawing.Graphics.DrawString%2A> Methode erfordert außerdem eine <xref:System.Drawing.Brush> und</span><span class="sxs-lookup"><span data-stu-id="07985-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and</span></span> <xref:System.Drawing.Font>  
  
 <span data-ttu-id="07985-106">Können Sie auch die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, die von der <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="07985-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <span data-ttu-id="07985-107">erfordert außerdem eine <xref:System.Drawing.Color> und <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="07985-107">also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="07985-108">Die folgende Abbildung zeigt die Ausgabe von Text zu einem bestimmten Zeitpunkt gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode.</span><span class="sxs-lookup"><span data-stu-id="07985-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![Screenshot mit der Ausgabe von Text zu einem bestimmten Zeitpunkt.](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="07985-110">Zeichnen einer Linie von Text mit GDI +</span><span class="sxs-lookup"><span data-stu-id="07985-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="07985-111">Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> Methode auf und übergibt Sie den gewünschten Text, <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, und <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="07985-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="07985-112">Zeichnen einer Linie von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="07985-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="07985-113">Verwenden der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode auf und übergibt Sie den gewünschten Text, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, und <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="07985-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07985-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="07985-114">Compiling the Code</span></span>  
 <span data-ttu-id="07985-115">Die vorherigen Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="07985-115">The previous examples require:</span></span>  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`<span data-ttu-id="07985-116">, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="07985-116">, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07985-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07985-117">See also</span></span>

- [<span data-ttu-id="07985-118">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="07985-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="07985-119">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="07985-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="07985-120">Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="07985-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="07985-121">Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck</span><span class="sxs-lookup"><span data-stu-id="07985-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
