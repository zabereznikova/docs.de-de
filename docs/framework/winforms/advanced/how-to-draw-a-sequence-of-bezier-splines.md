---
title: 'Vorgehensweise: Zeichnen Sie eine Sequenz von B&#233;Zier Splines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 1de2f44be189cb2ff874a748ae6093c945120178
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711789"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Vorgehensweise: Zeichnen Sie eine Sequenz von B&#233;Zier Splines
Können Sie die <xref:System.Drawing.Graphics.DrawBeziers%2A> Methode der <xref:System.Drawing.Graphics> Béziersplinekurven zum Zeichnen einer Sequenz von verbunden ist.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Kurve, die aus zwei verbundenen Béziersplinekurven besteht. Der Endpunkt die erste Béziersplinekurve ist der Ausgangspunkt der zweiten Béziersplinekurve.  
  
 Die folgende Abbildung zeigt die verbundenen Splines sowie die sieben Punkte.  
  
 ![Bezier-Spline](./media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Béziersplinekurven in GDI +](bezier-splines-in-gdi.md)
- [Erstellen und Zeichnen von Kurven](constructing-and-drawing-curves.md)
