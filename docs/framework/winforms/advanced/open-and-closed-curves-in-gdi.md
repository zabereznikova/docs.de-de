---
title: Offene und geschlossene Kurven in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: bc78077be45f22826eaa23a746dcf272601d51b4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711459"
---
# <a name="open-and-closed-curves-in-gdi"></a>Offene und geschlossene Kurven in GDI+
Die folgende Abbildung zeigt zwei Kurven geteilt: eine offene und eine geschlossen.  
  
 ![Offene und geschlossene Kurven](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Verwaltete Schnittstelle für die Kurven  
 Geschlossene Kurven ein inneres haben und können daher mit einem Pinsel gefüllt werden. Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Füllen geschlossene Formen und Kurven: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, und <xref:System.Drawing.Graphics.FillRegion%2A>. Wenn Sie eine der folgenden Methoden aufrufen, müssen Sie eine der bestimmten Pinseltyp übergeben (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, oder <xref:System.Drawing.Drawing2D.PathGradientBrush>) als Argument.  
  
 Die <xref:System.Drawing.Graphics.FillPie%2A> Methode ist eine Ergänzung für die <xref:System.Drawing.Graphics.DrawArc%2A> Methode. Ebenso wie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode zeichnet einen Teil der Kontur einer Ellipse, die <xref:System.Drawing.Graphics.FillPie%2A> Methode füllt einen Teil der das Innere einer Ellipse. Im folgenden Beispiel zeichnet einen Bogen und den entsprechenden Teil das Innere der Ellipse füllt:  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 Die folgende Abbildung zeigt den Bogen mit Strichen und der gefüllten Kreis.  
  
 ![Offene und geschlossene Kurven](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 Die <xref:System.Drawing.Graphics.FillClosedCurve%2A> Methode ist eine Ergänzung für die <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode. Beide Methoden schließen die Kurve automatisch durch das Verbinden des Endpunkts mit den Anfangspunkt, an. Das folgende Beispiel zeichnet eine Kurve, die durchlaufen (0, 0), (60, 20) und (40, 50). Die Kurve wird dann automatisch geschlossen, durch das Verbinden (40, 50) zum Ausgangspunkt (0, 0), und das innere mit einer Volltonfarbe gefüllt wird.  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt das Innere der separate Teile eines Pfads. Wenn ein Teil eines Pfads eine geschlossene Kurve oder Form bilden nicht die <xref:System.Drawing.Graphics.FillPath%2A> Methode dieser Teil des Pfads wird vor dem Ausfüllen es automatisch geschlossen wird. Im folgenden Beispiel wird gezeichnet, und füllt einen Pfad, der einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und einem Kreis besteht:  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 Die folgende Abbildung zeigt den Pfad mit und ohne die einfarbige Füllung. Beachten Sie, dass der Text in der Zeichenfolge wird beschrieben, aber nicht, durch ausgefüllt die <xref:System.Drawing.Graphics.DrawPath%2A> Methode. Es ist die <xref:System.Drawing.Graphics.FillPath%2A> -Methode, die die Innenflächen der Zeichen in der Zeichenfolge.  
  
 ![Zeichenfolge in einem Pfad](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md)
- [Erstellen und Zeichnen von Pfaden](constructing-and-drawing-paths.md)
