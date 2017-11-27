---
title: Grafikpfade in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e027228ea1cc047f213c28ac3a4984c2f0227c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="graphics-paths-in-gdi"></a>Grafikpfade in GDI+
Pfade werden durch Kombinieren von Linien, Rechtecke und einfachen Kurven gebildet. Beachten Sie aus der [Übersicht über Vektorgrafiken](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) , dass die folgenden grundlegenden Bausteine besonders hilfreich erwiesen haben für das Zeichnen von Bildern:  
  
-   Linien  
  
-   Rechtecke  
  
-   Ellipsen  
  
-   Bögen  
  
-   Polygone  
  
-   Kardinale Splinekurven  
  
-   Bézier-splines  
  
 In GDI + die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekts können Sie eine Sequenz diese Bausteine in einem Arbeitsschritt zusammenfassen. Die gesamte Sequenz von Linien, Rechtecke, Polygone und Kurven kann dann mit einem einzigen Aufruf gezeichnet werden die <xref:System.Drawing.Graphics.DrawPath%2A> Methode der <xref:System.Drawing.Graphics> Klasse. Die folgende Abbildung zeigt einen Pfad erstellt, indem eine Linie, einen Bogen, eine Béziersplinekurve und eine cardinal-Splinekurve kombiniert.  
  
 ![Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>Unter Verwendung eines Pfads  
 Die <xref:System.Drawing.Drawing2D.GraphicsPath> Klasse bietet die folgenden Methoden zum Erstellen einer Sequenz von Elementen, die gezeichnet werden soll: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (bei kardinale Splines) und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>. Jede dieser Methoden ist überladen wird. Jede Methode unterstützt, also mehrere unterschiedliche Parameterlisten. Z. B. eine Variation des der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> Methode empfängt, vier ganzen Zahlen und eine Variante dieses die <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> -Methode lässt zwei <xref:System.Drawing.Point> Objekte.  
  
 Die Methoden zum Hinzufügen von Linien, Rechtecke und Bézier-Splines in einen Pfad haben im plural Begleitmethoden, die mehrere Elemente, auf den Pfad in einem einzigen Aufruf hinzuzufügen: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>. Darüber hinaus die <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> Methoden verfügen über Begleitmethoden <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, hinzufügen, die eine geschlossene Kurve oder ein Kreis auf den Pfad.  
  
 Um einen Pfad zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> -Objekt, eine <xref:System.Drawing.Pen> -Objekt, und ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawPath%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um den Pfad zu rendern. Die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert die Sequenz von Linien und Kurven, die den Pfad bilden. Die <xref:System.Drawing.Pen> Objekt und die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt werden als Argumente übergeben der <xref:System.Drawing.Graphics.DrawPath%2A> Methode. Im folgende Beispiel zeichnet einen Pfad, der von einer Zeile und einer Ellipse, die eine Béziersplinekurve besteht aus:  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 Die folgende Abbildung zeigt den Pfad an.  
  
 ![Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Zusätzlich zum Hinzufügen von Linien, Rechtecke und Kurven auf einen Pfad ein, können Sie die Pfade zu einem Pfad hinzufügen. Dadurch können Sie die existierenden Pfade zu großen, komplexen Pfade zu kombinieren.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Es gibt zwei anderen Elementen können Sie einen Pfad hinzufügen: Zeichenfolgen und Kreissegmente. Ein Kreis ist ein Teil das Innere einer Ellipse. Das folgende Beispiel erstellt einen Pfad in einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und ein Kreis an:  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 Die folgende Abbildung zeigt den Pfad an. Beachten Sie, dass ein Pfad keinen verbunden sein; der Bogen, cardinal-Splinekurve, Zeichenfolgen- und Kreis werden getrennt.  
  
 ![Pfade](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
