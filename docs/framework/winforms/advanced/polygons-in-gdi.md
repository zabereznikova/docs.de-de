---
title: "Polygone in GDI+ | Microsoft Docs"
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
  - "Zeichnen, Polygone"
  - "GDI+, Polygone"
  - "Polygone"
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Polygone in GDI+
Ein Polygon ist eine geschlossene Form mit drei oder mehr geraden Seiten.  Beispielsweise ist ein Dreieck ein dreiseitiges Polygon, ein Rechteck ein vierseitiges Polygon und ein Fünfeck ein fünfseitiges Polygon.  Die folgende Abbildung zeigt mehrere Polygone.  
  
 ![Polygone](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.png "Aboutgdip02\_art07")  
  
## Zeichnen eines Polygons  
 Um ein Polygon zu zeichnen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt, ein <xref:System.Drawing.Pen>\-Objekt und ein Array von <xref:System.Drawing.Point>\- \(oder <xref:System.Drawing.PointF>\-\)Objekten.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die <xref:System.Drawing.Graphics.DrawPolygon%2A>\-Methode bereit.  Das <xref:System.Drawing.Pen>\-Objekt speichert Attribute für die Linie, mit der das Polygon gerendert wird, z. B. Linienstärke und \-farbe. Das Array aus <xref:System.Drawing.Point>\-Objekten speichert die Punkte, die durch Geraden miteinander verbunden werden müssen.  Das <xref:System.Drawing.Pen>\-Objekt und das <xref:System.Drawing.Point>\-Objektarray werden als Argumente an die <xref:System.Drawing.Graphics.DrawPolygon%2A>\-Methode übergeben.  Im folgenden Beispiel wird ein dreiseitiges Polygon gezeichnet.  Beachten Sie, dass  `myPointArray` nur drei Punkte enthält: \(0, 0\), \(50, 30\) und \(30, 60\).  Die <xref:System.Drawing.Graphics.DrawPolygon%2A>\-Methode schließt das Polygon automatisch, indem eine Linie von \(30, 60\) zurück zum Anfangspunkt \(0, 0\) gezogen wird.  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 Die folgende Abbildung zeigt das Polygon.  
  
 ![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.png "Aboutgdip02\_art08")  
  
## Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Erstellen eines Stiftes](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)