---
title: "Offene und geschlossene Kurven in GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kurven"
  - "Kurven, Zeichnen"
  - "Kurven, Füllen"
  - "GDI+, Kurven"
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Offene und geschlossene Kurven in GDI+
Die folgende Abbildung zeigt zwei Kurven: eine offene und eine geschlossene Kurve.  
  
 ![Offene und geschlossene Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.png "Aboutgdip02\_art24")  
  
## Verwaltete Schnittstelle für Kurven  
 Geschlossene Kurven weisen eine Innenfläche auf und können daher mit einem Pinsel gefüllt werden.  Die <xref:System.Drawing.Graphics>\-Klasse in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] enthält die folgenden Methoden zum Füllen geschlossener Formen und Kurven: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A> und <xref:System.Drawing.Graphics.FillRegion%2A>.  Sobald Sie eine dieser Methoden aufrufen, müssen Sie einen bestimmten Pinseltyp \(<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> oder <xref:System.Drawing.Drawing2D.PathGradientBrush>\) als Argument übergeben.  
  
 Die <xref:System.Drawing.Graphics.FillPie%2A>\-Methode ist eine Begleitmethode der <xref:System.Drawing.Graphics.DrawArc%2A>\-Methode.  Genauso wie die <xref:System.Drawing.Graphics.DrawArc%2A>\-Methode einen Teilabschnitt eines Ellipsenumrisses zeichnet, füllt die <xref:System.Drawing.Graphics.FillPie%2A>\-Methode ein Teilsegment der Innenfläche einer Ellipse.  Im folgenden Beispiel wird ein Bogen gezeichnet und der entsprechende Teil der Ellipseninnenfläche gefüllt:  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 Die folgende Abbildung zeigt den Bogen und das gefüllte Kreissegment.  
  
 ![Offene und geschlossene Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.png "Aboutgdip02\_art25")  
  
 Die <xref:System.Drawing.Graphics.FillClosedCurve%2A>\-Methode ist eine Begleitmethode der <xref:System.Drawing.Graphics.DrawClosedCurve%2A>\-Methode.  Beide Methoden schließen die Kurve automatisch, indem Sie den Endpunkt mit dem Anfangspunkt verbinden.  Im folgenden Beispiel wird eine Kurve gezeichnet, die durch die Punkte \(0, 0\), \(60, 20\) und \(40, 50\) verläuft.  Anschließend wird die Kurve automatisch geschlossen, indem der Punkt \(40, 50\) mit dem Anfangspunkt \(0, 0\) verbunden wird, und die Innenfläche wird mit einer Volltonfarbe gefüllt.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Die <xref:System.Drawing.Graphics.FillPath%2A>\-Methode füllt die Innenflächen der einzelnen Teilstücke eines Pfades.  Wenn ein Teilstück eines Pfades keine geschlossene Kurve oder Form bildet, schließt die <xref:System.Drawing.Graphics.FillPath%2A>\-Methode dieses Teilstück automatisch, bevor sie es füllt.  Im folgenden Beispiel wird ein Pfad aus einem Bogen, einem kardinalen Spline, einer Zeichenfolge und einem Kreissegment gezeichnet und gefüllt:  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 Die folgende Abbildung zeigt den Pfad mit und ohne Volltonfüllung.  Beachten Sie, dass der Text in der Zeichenfolge durch die <xref:System.Drawing.Graphics.DrawPath%2A>\-Methode zwar mit einem Umriss versehen, jedoch nicht gefüllt wird.  Die Innenflächen der Zeichen in der Zeichenfolge werden durch die <xref:System.Drawing.Graphics.FillPath%2A>\-Methode gefüllt.  
  
 ![Zeichenfolge in einem Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.png "Aboutgdip02\_art26")  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)