---
title: "B&#233;zier-Splines in GDI+ | Microsoft Docs"
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
  - "Béziersplinekurven"
  - "GDI+, Béziersplinekurven"
  - "Splines, Bézier"
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# B&#233;zier-Splines in GDI+
Ein Bézier\-Spline ist eine Kurve, die durch vier Punkte definiert wird: zwei Endpunkte \(p1 und p2\) und zwei Steuerpunkte \(c1 und c2\).  Die Kurve beginnt bei p1 und endet bei p2.  Die Kurve verläuft nicht durch die Steuerpunkte. Vielmehr fungieren diese Steuerpunkte als Magneten, die die Kurve in bestimmte Richtungen ziehen und die Krümmung der Kurve beeinflussen.  Die folgende Abbildung zeigt eine Bézier\-Kurve mit den End\- und Steuerpunkten.  
  
 ![Bézier&#45;Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.png "Aboutgdip02\_art11a")  
  
 Die Kurve beginnt bei p1 und verläuft in Richtung des Steuerpunktes c1.  Die Tangente der Kurve in p1 ist die Linie, die von p1 nach c1 gezogen wird.  Die Tangente im Endpunkt p2 ist die Linie, die von c2 nach p2 gezogen wird.  
  
## Zeichnen von Bézier\-Splines  
 Zum Zeichnen eines Bézier\-Splines benötigen Sie eine Instanz der <xref:System.Drawing.Graphics>\-Klasse sowie <xref:System.Drawing.Pen>.  Die Instanz der <xref:System.Drawing.Graphics>\-Klasse stellt die <xref:System.Drawing.Graphics.DrawBezier%2A>\-Methode bereit, und in <xref:System.Drawing.Pen> werden Attribute, z. B. Breite und Farbe, der zum Rendern der Kurve verwendeten Linie gespeichert.  <xref:System.Drawing.Pen> wird als eines der Argumente an die <xref:System.Drawing.Graphics.DrawBezier%2A>\-Methode übergeben.  Die übrigen Argumente, die an die <xref:System.Drawing.Graphics.DrawBezier%2A>\-Methode übergeben werden, sind die Endpunkte und die Steuerpunkte.  Im folgenden Beispiel wird ein Bézier\-Spline mit dem Anfangspunkt \(0, 0\), den Steuerpunkten \(40, 20\) und \(80, 150\) und dem Endpunkt \(100, 10\) gezeichnet:  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 Die folgende Abbildung zeigt die Kurve, die Steuerpunkte und zwei Tangenten.  
  
 ![Bézier&#45;Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.png "Aboutgdip02\_art12")  
  
 Bézier\-Splines wurden ursprünglich von Pierre Bézier für Entwürfe in der Autoindustrie entwickelt.  Seitdem haben sie sich in vielen CAD‑Bereichen als sehr nützlich erwiesen und werden auch zum Definieren des Umrisses von Schriften verwendet.  Bézier\-Splines können eine Vielzahl von Formen ergeben. Einige Formen sehen Sie in der folgenden Abbildung:  
  
 ![Pfade](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.png "Aboutgdip02\_art13")  
  
## Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Gewusst wie: Erstellen eines Stiftes](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)