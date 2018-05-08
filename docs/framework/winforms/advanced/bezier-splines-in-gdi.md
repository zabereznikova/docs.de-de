---
title: B&#233;Zier Splines in GDI +
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 2e247ec2bcd57c2fb2f5c32f61d38a2e7a267ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;Zier Splines in GDI +
Ein Bézier-Spline ist eine von vier Punkte angegebene Kurve: zwei Endpunkte (p1 und p2) und die beiden Steuerpunkte (c1 und c2). Die Kurve beginnt bei p1 und p2 endet. Leitet die Kurve nicht über die Steuerpunkte, aber die Steuerpunkte als Magnete, bestimmte erfahren Sie, wie die Kurve herausziehen und Schätzung vor bzw. beeinflusst die Möglichkeit Steuerpunkte fungieren. Die folgende Abbildung zeigt eine Bézier-Kurve zusammen mit den End- und Steuerpunkte.  
  
 ![Bézier-Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 Die Kurve beginnt bei p1 und gegen das Steuerelement zeigen c1 verschiebt. Die Tangente der Kurve in p1 ist die Zeile, die von p1 c1 gezeichnet. Die Tangente im Endpunkt P2 ist die Zeile zu p2 c2 gezeichnet.  
  
## <a name="drawing-bzier-splines"></a>Zeichnen von Bézier-Splines  
 Um eine Béziersplinekurve zu zeichnen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Pen>. Die Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawBezier%2A> -Methode, und die <xref:System.Drawing.Pen> speichert Attribute, z. B. Breite und Farbe der Linie, die zum Rendern der Kurve verwendet. Die <xref:System.Drawing.Pen> wird als eines der Argumente zu übergeben, die <xref:System.Drawing.Graphics.DrawBezier%2A> Methode. Die übrigen Argumente zu übergeben, um die <xref:System.Drawing.Graphics.DrawBezier%2A> Methode sind die Endpunkte und die Steuerpunkte. Im folgende Beispiel zeichnet eine Béziersplinekurve, mit dem Anfangspunkt (0, 0), Punkte (40, 20) und (80, 150) zu steuern, und den Endpunkt (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 Die folgende Abbildung zeigt die Kurve, die Steuerpunkte und zwei Tangenten.  
  
 ![Bézier-Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Bézier-Splines wurden ursprünglich von Pierre Bézier für den Entwurf in der Automobilindustrie entwickelt. Da sind aussagekräftig sind in vielen Arten von CAD / CAM erwiesen haben, und werden auch verwendet, um die Umrisse von Schriftarten zu definieren. Bézier-Splines können eine Vielzahl von Formen ergeben, von die einige in der folgenden Abbildung dargestellt sind.  
  
 ![Pfade](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Gewusst wie: Erstellen eines Stifts](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
