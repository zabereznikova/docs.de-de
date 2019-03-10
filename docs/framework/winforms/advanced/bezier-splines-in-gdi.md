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
ms.openlocfilehash: 7648f7f9da72abea4bfc87603eea290614294eff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707260"
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;Zier Splines in GDI +
Eine Béziersplinekurve ist eine Kurve, die durch vier Punkte angegeben: zwei Endpunkte (p1 und p2) und zwei Punkte (c1 und c2). Die Kurve p1 beginnt und endet bei p2. Die Kurve übergibt die nicht über die Kontrollpunkte, sondern die Control-Punkte als Magnetquellen, per Pull von der Kurve in bestimmte Anweisungen und einen Einfluss auf die Möglichkeit Steuerpunkte. Die folgende Abbildung zeigt eine Bézierkurve zusammen mit den End- und die Control-Punkte.  
  
 ![Bezier-Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 Die Kurve beginnt bei p1 und für das Steuerelement zeigen c1 verschiebt. Die Tangente der Kurve in p1 ist die Zeile, die von p1 zu c1 gezeichnet. Die Tangente im Endpunkt P2 ist die Zeile zu p2 c2 gezeichnet.  
  
## <a name="drawing-bzier-splines"></a>Zeichnen Béziersplinekurven  
 Um eine Béziersplinekurve Zeichnen zu können, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Pen>. Die Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawBezier%2A> -Methode, und die <xref:System.Drawing.Pen> speichert Attribute, z. B. Breite und Farbe der Linie, die zum Rendern der Kurve verwendet. Die <xref:System.Drawing.Pen> wird als eines der Argumente zu übergeben, die <xref:System.Drawing.Graphics.DrawBezier%2A> Methode. Die übrigen Argumente übergeben werden, um die <xref:System.Drawing.Graphics.DrawBezier%2A> Methode sind die Endpunkte und die Kontrollpunkte. Im folgende Beispiel zeichnet eine Béziersplinekurve mit dem Anfangspunkt (0, 0), Punkt ("40", "20") und (80, 150) zu steuern und dem Endpunkt (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 Die folgende Abbildung zeigt die Kurve, die Control-Punkte und zwei Tangenten.  
  
 ![Bezier-Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Béziersplinekurven wurden ursprünglich von Pierre Bézier für den Entwurf in der Automobilindustrie entwickelt. Sie haben da belegt, dass Sie in vielen Arten von CAD / CAM nützlich und werden auch verwendet, um die Umrisse von Schriftarten zu definieren. Béziersplinekurven können eine Vielzahl von Formen ergeben, von die einige in der folgenden Abbildung angezeigt werden.  
  
 ![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Erstellen und Zeichnen von Kurven](constructing-and-drawing-curves.md)
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md)
- [Vorgehensweise: Erstellen eines Stifts](how-to-create-a-pen.md)
