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
ms.openlocfilehash: 47f420184ac384ab11054d1cc3e767ab7f618234
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="open-and-closed-curves-in-gdi"></a>Offene und geschlossene Kurven in GDI+
Die folgende Abbildung zeigt zwei Kurven: eine offene und eine geschlossen.  
  
 ![Offene und geschlossene Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Verwaltete Schnittstelle für Kurven  
 Geschlossene Kurven dem inneren haben und daher mit einem Pinsel ausgefüllt werden können. Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Füllen geschlossener Formen und Kurven: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, und <xref:System.Drawing.Graphics.FillRegion%2A>. Wenn Sie eine der folgenden Methoden aufrufen, müssen Sie einen der Pinseltypen bestimmten übergeben (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, oder <xref:System.Drawing.Drawing2D.PathGradientBrush>) als Argument.  
  
 Die <xref:System.Drawing.Graphics.FillPie%2A> Methode ist eine Ergänzung zu den <xref:System.Drawing.Graphics.DrawArc%2A> Methode. Ebenso wie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode zeichnet einen Teil der Kontur einer Ellipse, die <xref:System.Drawing.Graphics.FillPie%2A> Methode füllt einen Teil der das Innere einer Ellipse. Im folgenden Beispiel zeichnet einen Bogen und füllt den betreffenden Teil das Innere der Ellipse:  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 Die folgende Abbildung zeigt den Bogen und der ausgefüllte Kreis.  
  
 ![Offene und geschlossene Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 Die <xref:System.Drawing.Graphics.FillClosedCurve%2A> Methode ist eine Ergänzung zu den <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode. Beide Methoden schließen die Kurve automatisch durch Herstellen einer Verbindung den Endpunkt auf den Startpunkt. Im folgende Beispiel zeichnet eine Kurve, die durchlaufen (0, 0), (60, 20) und (40, 50). Die Kurve wird dann automatisch geschlossen, durch Herstellen einer Verbindung (40, 50) zum Anfangspunkt (0, 0), und das innere mit einer Volltonfarbe gefüllt wird.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt das Innere der separate Teile eines Pfads. Wenn ein Teil eines Pfads einen geschlossenen Kurve oder eine Form, bilden keine der <xref:System.Drawing.Graphics.FillPath%2A> Methode dieser Teil des Pfads wird vor dem Ausfüllen es automatisch geschlossen wird. Im folgenden Beispiel zeichnet und füllt einen Pfad, der einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und einem Kreis besteht:  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 Die folgende Abbildung zeigt den Pfad mit und ohne die einfarbige Füllung. Beachten Sie, dass der Text in der Zeichenfolge beschrieben wird, aber nicht, indem ausgefüllt die <xref:System.Drawing.Graphics.DrawPath%2A> Methode. Es ist die <xref:System.Drawing.Graphics.FillPath%2A> -Methode, die die Innenflächen der Zeichen in der Zeichenfolge.  
  
 ![Zeichenfolge in einem Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
