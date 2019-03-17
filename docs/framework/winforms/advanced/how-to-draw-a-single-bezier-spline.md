---
title: 'Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 0731595dc25b1afb4b3dbcc7eedbfb92ef32d267
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "58126278"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="02da6-102">Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline</span><span class="sxs-lookup"><span data-stu-id="02da6-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="02da6-103">Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt beiden Steuerpunkte und einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="02da6-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02da6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02da6-104">Example</span></span>  
 <span data-ttu-id="02da6-105">Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) "und" Endpunkt (200, 100).</span><span class="sxs-lookup"><span data-stu-id="02da6-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="02da6-106">Das Steuerelement zeigt sind ("100", "10") und (150, 150).</span><span class="sxs-lookup"><span data-stu-id="02da6-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="02da6-107">Die folgende Abbildung zeigt die resultierende Béziersplinekurve zusammen mit der Start, zeigen Sie Control-Punkte und Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="02da6-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="02da6-108">Die Abbildung zeigt auch die konvexe Hülle der Kurve, die ein Polygon durch Verbinden der vier Punkte mit geraden formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="02da6-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![Veranschaulicht einen Bezier-Spline.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="02da6-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="02da6-110">Compiling the Code</span></span>  
 <span data-ttu-id="02da6-111">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="02da6-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02da6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02da6-112">See also</span></span>
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="02da6-113">Béziersplinekurven in GDI +</span><span class="sxs-lookup"><span data-stu-id="02da6-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="02da6-114">Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven</span><span class="sxs-lookup"><span data-stu-id="02da6-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
