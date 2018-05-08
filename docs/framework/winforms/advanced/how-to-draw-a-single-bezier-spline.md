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
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline
Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt, die beiden Steuerpunkte und einen Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) und Endpunkt (200, 100). Das Steuerelement zeigt sind (100, 10) und (150, 150).  
  
 Die folgende Abbildung zeigt die resultierenden Béziersplinekurve sowie dessen Startpunkt, Steuerpunkte und Endpunkt. Die Abbildung zeigt auch die Splinekurve konvexe Hülle, also ein Polygon gebildet, indem Sie die vier Punkte mit geraden verbindet.  
  
 ![Bézier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [Bézier-Splines in GDI +](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Gewusst wie: Zeichnen einer Folge von Bézier-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
