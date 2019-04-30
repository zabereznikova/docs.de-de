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
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004240"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="3db93-102">Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline</span><span class="sxs-lookup"><span data-stu-id="3db93-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="3db93-103">Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt beiden Steuerpunkte und einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="3db93-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db93-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3db93-104">Example</span></span>  
 <span data-ttu-id="3db93-105">Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) "und" Endpunkt (200, 100).</span><span class="sxs-lookup"><span data-stu-id="3db93-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="3db93-106">Das Steuerelement zeigt sind ("100", "10") und (150, 150).</span><span class="sxs-lookup"><span data-stu-id="3db93-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="3db93-107">Die folgende Abbildung zeigt die resultierende Béziersplinekurve zusammen mit der Start, zeigen Sie Control-Punkte und Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="3db93-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="3db93-108">Die Abbildung zeigt auch die konvexe Hülle der Kurve, die ein Polygon durch Verbinden der vier Punkte mit geraden formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="3db93-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![Veranschaulicht einen Bezier-Spline.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3db93-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3db93-110">Compiling the Code</span></span>  
 <span data-ttu-id="3db93-111">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="3db93-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db93-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3db93-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="3db93-113">Béziersplinekurven in GDI +</span><span class="sxs-lookup"><span data-stu-id="3db93-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="3db93-114">Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven</span><span class="sxs-lookup"><span data-stu-id="3db93-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
