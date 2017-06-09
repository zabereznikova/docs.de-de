---
title: "Ellipsen und B&#246;gen in GDI+ | Microsoft Docs"
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
  - "Bögen"
  - "Zeichnen, Bögen"
  - "Zeichnen, Ellipsen"
  - "Ellipsen"
  - "GDI+, Bögen"
  - "GDI+, Ellipsen"
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Ellipsen und B&#246;gen in GDI+
Ellipsen und Bögen können Sie problemlos mit der <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode und der <xref:System.Drawing.Graphics.DrawArc%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse zeichnen.  
  
## Zeichnen einer Ellipse  
 Um eine Ellipse zu zeichnen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt und ein <xref:System.Drawing.Pen>\-Objekt.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode bereit. Das <xref:System.Drawing.Pen>\-Objekt speichert Attribute, z. B. Farbe und Stärke der Linie, mit der die Ellipse gerendert wird.  Das <xref:System.Drawing.Pen>\-Objekt wird als eines der Argumente an die <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode übergeben.  Die übrigen an die <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode übergebenen Argumente geben das umschließende Rechteck für die Ellipse an.  Die folgende Abbildung zeigt eine Ellipse und das zugehörige umschließende Rechteck.  
  
 ![Ellipsen und Bögen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.png "Aboutgdip02\_art05")  
  
 Im folgenden Beispiel wird eine Ellipse gezeichnet, deren umschließendes Rechteck eine Breite von 80, eine Höhe von 40 und seine linke obere Ecke im Punkt \(100, 50\) hat:  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 Da es sich bei <xref:System.Drawing.Graphics.DrawEllipse%2A> um eine überladene Methode der <xref:System.Drawing.Graphics>\-Klasse handelt, können Sie auf verschiedene Weisen Argumente für die Methode bereitstellen.  Beispielsweise können Sie ein <xref:System.Drawing.Rectangle> erstellen und <xref:System.Drawing.Rectangle> als Argument an die <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode übergeben:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## Zeichnen eines Bogens  
 Ein Bogen ist ein Segment einer Ellipse.  Zum Zeichnen eines Bogens müssen Sie die <xref:System.Drawing.Graphics.DrawArc%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse aufrufen.  Die Parameter der <xref:System.Drawing.Graphics.DrawArc%2A>\-Methode entsprechen denen der <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode, mit der Ausnahme, dass <xref:System.Drawing.Graphics.DrawArc%2A> einen Anfangswinkel und einen Bogenwinkel erfordert.  Im folgenden Beispiel wird ein Bogen mit einem Anfangswinkel von 30 Grad und einem Bogenwinkel von 180 Grad gezeichnet:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 Die folgende Abbildung zeigt den Bogen, die Ellipse und das umschließende Rechteck.  
  
 ![Ellipsen und Bögen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.png "Aboutgdip02\_art06")  
  
## Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Gewusst wie: Erstellen eines Stiftes](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Gewusst wie: Zeichnen der Kontur einer Form](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)