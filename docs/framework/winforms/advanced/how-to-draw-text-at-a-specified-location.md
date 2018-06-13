---
title: 'Gewusst wie: Zeichnen von Text an einer angegebenen Position'
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
ms.openlocfilehash: e55afd0629c1b9e6d30c8b31116ec28a718fcb4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523171"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="6cf8d-102">Gewusst wie: Zeichnen von Text an einer angegebenen Position</span><span class="sxs-lookup"><span data-stu-id="6cf8d-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="6cf8d-103">Wenn Sie benutzerdefinierte Zeichnung zu erstellen, können Sie Text in einer einzelnen horizontalen Linie ab, zu einem bestimmten Zeitpunkt zeichnen.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="6cf8d-104">Sie können auf diese Weise Text zeichnen, mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, der die <xref:System.Drawing.Graphics> -Klasse, akzeptiert eine <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF> Parameter.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="6cf8d-105">Die <xref:System.Drawing.Graphics.DrawString%2A> Methode erfordert außerdem eine <xref:System.Drawing.Brush> und <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="6cf8d-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="6cf8d-106">Können Sie auch die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, der die <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="6cf8d-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> Außerdem erfordert eine <xref:System.Drawing.Color> und ein <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="6cf8d-108">Die folgende Abbildung zeigt die Ausgabe von Text zu einem bestimmten Zeitpunkt gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="6cf8d-109">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="6cf8d-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="6cf8d-110">Zum Zeichnen einer Linie von Text mit GDI +</span><span class="sxs-lookup"><span data-stu-id="6cf8d-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="6cf8d-111">Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> -Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, und <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="6cf8d-112">Zum Zeichnen einer Linie von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="6cf8d-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="6cf8d-113">Verwenden der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, und <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6cf8d-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6cf8d-114">Compiling the Code</span></span>  
 <span data-ttu-id="6cf8d-115">Die vorherigen Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cf8d-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="6cf8d-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, ein Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="6cf8d-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf8d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cf8d-117">See Also</span></span>  
 [<span data-ttu-id="6cf8d-118">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="6cf8d-118">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="6cf8d-119">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="6cf8d-119">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="6cf8d-120">Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="6cf8d-120">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="6cf8d-121">Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck</span><span class="sxs-lookup"><span data-stu-id="6cf8d-121">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
