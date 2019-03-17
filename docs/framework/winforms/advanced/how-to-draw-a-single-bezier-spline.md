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
# <a name="how-to-draw-a-single-b233zier-spline"></a>Vorgehensweise: Zeichnen einer einzigen B&#233;Zier Spline
Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt beiden Steuerpunkte und einen Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) "und" Endpunkt (200, 100). Das Steuerelement zeigt sind ("100", "10") und (150, 150).  
  
 Die folgende Abbildung zeigt die resultierende Béziersplinekurve zusammen mit der Start, zeigen Sie Control-Punkte und Endpunkt. Die Abbildung zeigt auch die konvexe Hülle der Kurve, die ein Polygon durch Verbinden der vier Punkte mit geraden formatiert ist.  
  
 ![Veranschaulicht einen Bezier-Spline.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Béziersplinekurven in GDI +](bezier-splines-in-gdi.md)
- [Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven](how-to-draw-a-sequence-of-bezier-splines.md)
