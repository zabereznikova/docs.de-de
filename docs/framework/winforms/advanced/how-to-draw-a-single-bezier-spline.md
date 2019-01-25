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
ms.openlocfilehash: 32fc09c7525b40daea8c8705c43100cea0c052bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676457"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline
Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt beiden Steuerpunkte und einen Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) "und" Endpunkt (200, 100). Das Steuerelement zeigt sind ("100", "10") und (150, 150).  
  
 Die folgende Abbildung zeigt die resultierende Béziersplinekurve zusammen mit der Start, zeigen Sie Control-Punkte und Endpunkt. Die Abbildung zeigt auch die konvexe Hülle der Kurve, die ein Polygon durch Verbinden der vier Punkte mit geraden formatiert ist.  
  
 ![Bezier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Béziersplinekurven in GDI +](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)
- [Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
