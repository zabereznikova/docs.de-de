---
title: Grafikpfade in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 55cd3284f331e9793a0bb73f26ed16bbd99fa116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685647"
---
# <a name="graphics-paths-in-gdi"></a>Grafikpfade in GDI+
Pfade werden durch die Kombination von Linien, Rechtecke und einfache Kurven gebildet. Erinnern Sie sich an den [Übersicht über Vektorgrafiken](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) , dass die folgenden grundlegenden Bausteine der am häufigsten für das Zeichnen von Bildern nützlich erwiesen haben:  
  
-   Linien  
  
-   Rechtecke  
  
-   Ellipsen  
  
-   Bögen  
  
-   Polygone  
  
-   Kardinale splines  
  
-   Béziersplinekurven  
  
 In GDI + die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt können Sie eine Sequenz von diese Bausteine in einer einzigen Einheit zu erfassen. Die gesamte Sequenz aus Linien, Rechtecke, Polygone und Kurven kann dann mit einem einzigen Aufruf gezeichnet werden die <xref:System.Drawing.Graphics.DrawPath%2A> Methode der <xref:System.Drawing.Graphics> Klasse. Die folgende Abbildung zeigt einen Pfad durch Kombination einer Zeile, einen Bogen, eine Béziersplinekurve und eine cardinal-Splinekurve erstellt.  
  
 ![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>Mithilfe eines Pfads  
 Die <xref:System.Drawing.Drawing2D.GraphicsPath> Klasse stellt die folgenden Methoden zum Erstellen einer Sequenz von Elementen, die gezeichnet werden soll: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (für kardinale Splines), und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>. Jede dieser Methoden überladen wird. Jede Methode unterstützt, d. h. mehrere unterschiedliche Parameterlisten. Z. B. eine Variante der der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> Methode empfängt, vier ganzen Zahlen, und eine andere Variante des der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> -Methode empfängt zwei <xref:System.Drawing.Point> Objekte.  
  
 Die Methoden zum Hinzufügen von Linien, Rechtecke und Béziersplinekurven zu einem Pfad haben im plural Begleitmethoden, die den Pfad in einem einzigen Aufruf mehrere Elemente hinzugefügt: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>. Darüber hinaus die <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> Methoden verfügen über zugehörige Methoden, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, hinzufügen, die eine geschlossene Kurve oder ein Kreis auf den Pfad.  
  
 Um einen Pfad zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt eine <xref:System.Drawing.Pen> Objekt und ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawPath%2A> -Methode, und die <xref:System.Drawing.Pen> -Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um den Pfad zu rendern. Die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert die Sequenz von Linien und Kurven, die den Pfad zu bilden. Die <xref:System.Drawing.Pen> Objekt und die <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt übergeben werden, als Argumente für die <xref:System.Drawing.Graphics.DrawPath%2A> Methode. Das folgende Beispiel zeichnet einen Pfad, der eine Zeile und eine Ellipse eine Béziersplinekurve besteht:  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 Die folgende Abbildung zeigt den Pfad an.  
  
 ![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Zusätzlich zum Hinzufügen von Linien, Rechtecke und Kurven in einen Pfad, können Sie Pfade zu einem Pfad hinzufügen. Dadurch können Sie vorhandene Pfade zu großen, komplexen Pfaden zu kombinieren.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Es gibt zwei weitere Elemente können Sie einen Pfad hinzufügen: Zeichenfolgen und Kreisen. Ein Kreis ist ein Teil das Innere einer Ellipse an. Das folgende Beispiel erstellt einen Pfad in einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und einem Kreis dargestellt:  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 Die folgende Abbildung zeigt den Pfad an. Beachten Sie, dass ein Pfad nicht verbunden sein. der Bogen, cardinal-Splinekurve, Zeichenfolgen- und Kreis werden getrennt.  
  
 ![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
