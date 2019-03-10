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
ms.openlocfilehash: 6fc4e12bb7532019a0571095263b5447e4b0d1ed
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702515"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline
Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt beiden Steuerpunkte und einen Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) "und" Endpunkt (200, 100). Das Steuerelement zeigt sind ("100", "10") und (150, 150).  
  
 Die folgende Abbildung zeigt die resultierende Béziersplinekurve zusammen mit der Start, zeigen Sie Control-Punkte und Endpunkt. Die Abbildung zeigt auch die konvexe Hülle der Kurve, die ein Polygon durch Verbinden der vier Punkte mit geraden formatiert ist.  
  
 ![Bezier-Spline](./media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Béziersplinekurven in GDI +](bezier-splines-in-gdi.md)
- [Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven](how-to-draw-a-sequence-of-bezier-splines.md)
