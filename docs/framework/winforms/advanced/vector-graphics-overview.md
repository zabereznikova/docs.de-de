---
title: "&#220;bersicht &#252;ber Vektorgrafiken | Microsoft Docs"
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
  - "Koordinatensysteme"
  - "Grafiken, Vektorgrafiken"
  - "inclusive-inclusive-Endpunkte"
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# &#220;bersicht &#252;ber Vektorgrafiken
Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Linien, Rechtecke und andere Formen in einem Koordinatensystem zeichnen.  Sie können aus verschiedenen Koordinatensystemen auswählen. Das Standardkoordinatensystem hat immer den Ursprung in der linken oberen Ecke, die x‑Achse zeigt nach rechts und die y‑Achse zeigt nach unten.  Die Maßeinheit im Standardkoordinatensystem ist Pixel.  
  
## Die Bausteine von GDI\+  
 ![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.png "AboutGdip02\_Art01")  
  
 Auf einem Computerbildschirm wird die Anzeige in einem rechteckigen Array von Punkten, den so genannten Pixel, erstellt.  Die Anzahl der dargestellten Pixel ist von Bildschirm zu Bildschirm verschieden und kann in der Regel zu einem gewissen Grad vom Benutzer konfiguriert werden.  
  
 ![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.png "AboutGdip02\_Art02")  
  
 Wenn Sie mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] eine Linie, ein Rechteck oder eine Kurve zeichnen, stellen Sie bestimmte Schlüsselinformationen über das zu zeichnende Element bereit.  Beispielsweise können Sie eine Linie angeben, indem Sie zwei Punkte festlegen, oder ein Rechteck, indem Sie einen Punkt sowie einen Wert für die Höhe und Breite festlegen.  Zusammen mit dem Bildschirmtreiber ermittelt [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], welche Pixel für die Anzeige der Linie, des Rechtecks oder der Kurve aktiviert werden müssen.  Die folgende Abbildung zeigt die Pixel, die eingeschaltet werden, um eine Linie von Punkt \(4, 2\) zu Punkt \(12, 8\) darzustellen.  
  
 ![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.png "AboutGdip02\_Art03")  
  
 Im Laufe der Zeit haben sich bestimmte grundlegende Bausteine als besonders nützlich für die Erstellung von zweidimensionalen Bildern erwiesen.  Im Folgenden eine Liste dieser Bausteine, die alle von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] unterstützt werden:  
  
-   Linien  
  
-   Rechtecke  
  
-   Ellipsen  
  
-   Bögen  
  
-   Polygone  
  
-   Kardinale Splines  
  
-   Bézier\-Splines  
  
## Methoden zum Zeichnen mit einem Graphics\-Objekt  
 Die <xref:System.Drawing.Graphics>\-Klasse in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Zeichnen der Elemente in der vorherigen Liste: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> \(für kardinale Splines\) und <xref:System.Drawing.Graphics.DrawBezier%2A>.  Jede dieser Methoden ist überladen, d. h. jede Methode unterstützt mehrere verschiedene Parameterlisten.  Eine Variante der <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode erhält beispielsweise ein <xref:System.Drawing.Pen>\-Objekt und vier ganze Zahlen, während eine andere Variante der <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode ein <xref:System.Drawing.Pen>\-Objekt und zwei <xref:System.Drawing.Point>\-Objekte erhält.  
  
 Die Methoden zum Zeichnen von Linien, Rechtecken und Bézier\-Splines verfügen über mehrere Begleitmethoden, durch die mehrere Elemente in einem einzelnen Aufruf gezeichnet werden: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A> und <xref:System.Drawing.Graphics.DrawBeziers%2A>.  Außerdem hat die <xref:System.Drawing.Graphics.DrawCurve%2A>\-Methode die Begleitmethode <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, die eine Kurve durch Verbinden des Endpunktes der Kurve mit dem Anfangspunkt schließt.  
  
 Alle Zeichenmethoden der <xref:System.Drawing.Graphics>\-Klasse funktionieren in Verbindung mit einem <xref:System.Drawing.Pen>\-Objekt.  Um ein Element zu zeichnen, müssen Sie mindestens zwei Objekte erstellen: ein <xref:System.Drawing.Graphics>\-Objekt und ein <xref:System.Drawing.Pen>\-Objekt.  Das <xref:System.Drawing.Pen>\-Objekt speichert Attribute des zu zeichnenden Elements, z. B. Linienstärke und \-farbe.  Das <xref:System.Drawing.Pen>\-Objekt wird als eines der Argumente an die Zeichenmethode übergeben.  Eine Variante der <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode erhält beispielsweise ein <xref:System.Drawing.Pen>\-Objekt und vier ganze Zahlen. Dies wird im folgenden Beispiel gezeigt, bei dem ein Rechteck mit einer Breite von 100, einer Höhe von 50 und der linken oberen Ecke im Punkt \(20, 10\) gezeichnet wird:  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)