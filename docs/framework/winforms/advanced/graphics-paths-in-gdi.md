---
title: "Grafikpfade in GDI+ | Microsoft Docs"
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
  - "Zeichnen, Pfade"
  - "GDI+, Zeichnen von Pfaden"
  - "Grafiken, Pfade"
  - "Pfade, Zeichnen"
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Grafikpfade in GDI+
Pfade werden durch Kombinieren von Linien, Rechtecken und einfachen Kurven gebildet.  Wie bereits unter [Übersicht über Vektorgrafiken](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) erläutert, haben sich die folgenden Grundbausteine als die sinnvollsten Elemente zum Zeichnen von Bildern erwiesen:  
  
-   Linien  
  
-   Rechtecke  
  
-   Ellipsen  
  
-   Bögen  
  
-   Polygone  
  
-   Kardinale Splines  
  
-   Bézier\-Splines  
  
 In GDI\+ können Sie mit dem <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt eine Sequenz solcher Bausteine zu einer einzigen Einheit zusammenfassen.  Die gesamte Sequenz aus Linien, Rechtecken, Polygonen und Kurven kann dann mit einem einzigen Aufruf der <xref:System.Drawing.Graphics.DrawPath%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse gezeichnet werden.  Die folgende Abbildung zeigt einen Pfad, der durch Kombination einer Linie mit einem Bogen, einem Bézier\-Spline und einem kardinalen Spline erstellt wird.  
  
 ![Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.png "Aboutgdip02\_art14")  
  
## Verwenden eines Pfades  
 Die <xref:System.Drawing.Drawing2D.GraphicsPath>\-Klasse stellt die folgenden Methoden zum Erstellen einer Sequenz von Zeichenelementen bereit: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> \(für kardinale Splines\) und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.  Jede dieser Methoden ist überladen, d. h. jede Methode unterstützt mehrere verschiedene Parameterlisten.  Eine Variante der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>\-Methode erhält beispielsweise vier ganze Zahlen, während eine andere Variante der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>\-Methode zwei <xref:System.Drawing.Point>\-Objekte erhält.  
  
 Die Methoden zum Hinzufügen von Linien, Rechtecken und Bézier\-Splines zu einem Pfad verfügen über mehrere Begleitmethoden, durch die dem Pfad in einem einzelnen Aufruf mehrere Elemente hinzugefügt werden: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.  Darüber hinaus verfügen die Methoden <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> über die Begleitmethoden <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, durch die dem Pfad eine geschlossene Kurve bzw. ein geschlossener Kreis hinzugefügt wird.  
  
 Um einen Pfad zu zeichnen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt, ein <xref:System.Drawing.Pen>\-Objekt und ein <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die <xref:System.Drawing.Graphics.DrawPath%2A>\-Methode bereit. Das <xref:System.Drawing.Pen>\-Objekt speichert Attribute, z. B. Farbe und Stärke der Linie, mit der der Pfad gerendert wird.  Das <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt speichert die Sequenz von Linien und Kurven, die den Pfad bilden.  Die Objekte <xref:System.Drawing.Pen> und <xref:System.Drawing.Drawing2D.GraphicsPath> werden der <xref:System.Drawing.Graphics.DrawPath%2A>\-Methode als Argumente übergeben.  Im folgenden Beispiel wird ein Pfad gezeichnet, der aus einer Linie, einer Ellipse und einem Bézier\-Spline besteht:  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 Die folgende Abbildung zeigt den Pfad.  
  
 ![Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.png "Aboutgdip02\_art15")  
  
 Zusätzlich zu Linien, Rechtecken und Kurven können Sie einem Pfad auch Pfade hinzufügen.  Dadurch können Sie vorhandene Pfade zu komplexen Pfaden zusammenfügen.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Zwei weitere Elemente können einem Pfad hinzugefügt werden: Zeichenfolgen und Kreissegmente.  Ein Kreissegment ist ein Teil der Innenfläche einer Ellipse.  Im folgenden Beispiel wird ein Pfad aus einem Bogen, einem kardinalen Spline, einer Zeichenfolge und einem Kreissegment erstellt:  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 Die folgende Abbildung zeigt den Pfad.  Beachten Sie, dass ein Pfad nicht durchgängig sein muss. Der Bogen, der kardinale Spline, die Zeichenfolge und das Kreissegment sind getrennte Elemente.  
  
 ![Pfade](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.png "Aboutgdip02\_Art16")  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)