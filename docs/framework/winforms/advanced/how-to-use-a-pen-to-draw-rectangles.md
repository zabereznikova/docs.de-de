---
title: 'Vorgehensweise: Verwenden eines Stiftes zum Zeichnen von Rechtecken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: a29cae5a360185b7fa5e70fc0181c0cfaac8fc09
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463188"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="36d36-102">Vorgehensweise: Verwenden eines Stiftes zum Zeichnen von Rechtecken</span><span class="sxs-lookup"><span data-stu-id="36d36-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="36d36-103">Zum Zeichnen von Rechtecken, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="36d36-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="36d36-104">Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawRectangle%2A> -Methode, und die <xref:System.Drawing.Pen> Objektspeicher Features der Zeile, z. B. Farbe und Breite.</span><span class="sxs-lookup"><span data-stu-id="36d36-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36d36-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36d36-105">Example</span></span>  
 <span data-ttu-id="36d36-106">Im folgende Beispiel zeichnet ein Rechteck mit der linken oberen Ecke auf (10, 10).</span><span class="sxs-lookup"><span data-stu-id="36d36-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="36d36-107">Das Rechteck hat eine Breite von 100 und eine Höhe von 50.</span><span class="sxs-lookup"><span data-stu-id="36d36-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="36d36-108">Das zweite Argument übergeben wird, um die <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor gibt an, dass die Stiftbreite 5 Pixel.</span><span class="sxs-lookup"><span data-stu-id="36d36-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="36d36-109">Wenn das Rechteck gezeichnet wird, wird der Stift auf der Begrenzung des Rechtecks zentriert.</span><span class="sxs-lookup"><span data-stu-id="36d36-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="36d36-110">Da die Stiftbreite 5 ist, sind die Seiten des Rechtecks gezeichnet 5 Pixel breit, z. B. 1 Pixel gezeichnet wird auf die Begrenzung selbst, 2 Pixel gezeichnet werden, innerhalb und außerhalb 2 Pixel gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="36d36-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="36d36-111">Weitere Details zu Stift Ausrichtung, finden Sie unter [Vorgehensweise: Festlegen von Stiftbreite und-Ausrichtung](how-to-set-pen-width-and-alignment.md).</span><span class="sxs-lookup"><span data-stu-id="36d36-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="36d36-112">Die folgende Abbildung zeigt das sich ergebende Rechteck.</span><span class="sxs-lookup"><span data-stu-id="36d36-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="36d36-113">Die gepunkteten Linien anzeigen, in denen das Rechteck gezeichnet worden wäre, wenn die Stiftbreite pixelweise gewesen wäre.</span><span class="sxs-lookup"><span data-stu-id="36d36-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="36d36-114">Die vergrößerte Ansicht von der linken oberen Ecke des Rechtecks zeigt, dass die dicken schwarzen Linien auf die gepunktete Linien zentriert werden.</span><span class="sxs-lookup"><span data-stu-id="36d36-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![Screenshot, der das gezeichnete Rechteck mit Schwarz und gepunkteten Linien anzeigt.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="36d36-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="36d36-116">Compiling the Code</span></span>  
 <span data-ttu-id="36d36-117">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="36d36-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d36-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36d36-118">See also</span></span>
- [<span data-ttu-id="36d36-119">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="36d36-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
