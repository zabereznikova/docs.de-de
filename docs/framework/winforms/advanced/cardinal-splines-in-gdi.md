---
title: "Kardinale Splines in GDI+ | Microsoft Docs"
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
  - "Kardinale Splinekurven"
  - "GDI+, Kardinale Splinekurven"
  - "Splines, Kardinal"
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Kardinale Splines in GDI+
Ein kardinaler Spline ist eine Folge von einzelnen Kurven, die zu einer größeren Kurve zusammengefügt wurden.  Der Spline wird durch ein Array aus Punkten und einen Spannungsparameter angegeben.  Ein kardinaler Spline läuft gleichmäßig durch jeden Punkt in dem Array, d. h. im Verlauf der Kurve entstehen keine Ecken oder abrupten Spannungswechsel.  Die folgende Abbildung zeigt einen Satz von Punkten und einen kardinalen Spline, der durch jeden Punkt läuft.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.png "Aboutgdip02\_art09")  
  
## Physikalische und mathematische Splines  
 Ein physikalisch vorhandener Spline ist ein dünnes Stück Holz oder eine Leiste aus einem anderen biegsamen Material.  Vor dem Aufkommen von mathematischen Splines verwendete der Konstrukteur physikalische Splines zum Zeichnen von Kurven.  Dabei legte er den Spline auf einen Bogen Papier und fixierte ihn an mehreren gegebenen Punkten.  Anschließend konnte er eine Kurve zeichnen, indem er einen Stift an dem Spline entlangzog.  Ein Satz Punkte kann eine Vielzahl von Kurven ergeben, je nach den Eigenschaften des physikalischen Splines.  So ergibt sich beispielsweise bei einem Spline mit einem hohen Biegewiderstand eine andere Kurve als bei einem extrem biegsamen Spline.  
  
 Die Formeln für mathematische Splines basieren auf den Eigenschaften von biegsamen Leisten. Daher ähneln die Kurven, die mit mathematischen Splines erstellt werden, den Kurven, die einst mit diesen Leisten gezeichnet wurden.  Wie bei physikalischen Splines ergeben sich auch bei mathematischen Splines mit unterschiedlicher Spannung unterschiedliche Kurven, die durch die gleichen Punkte verlaufen.  Die folgende Abbildung zeigt vier kardinale Splines, die durch die gleichen Punkte verlaufen.  Für jeden Spline wird die Spannung angezeigt.  Die Spannung 0 entspricht einer unendlichen physikalischen Spannung, wodurch erzwungen wird, dass die Kurve die kürzeste Strecke zwischen den Punkten einnimmt \(also eine Gerade\).  Die Spannung 1 bedeutet keine physikalische Spannung, wodurch der Spline den Verlauf mit der geringsten Gesamtbiegung einnimmt.  Bei Spannungswerten über 1 verhält sich die Kurve wie eine zusammengedrückte Spiralfeder, deren Pfad umso länger ist, je mehr sie zusammengedrückt wird.  
  
 ![Kardinale Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.png "Aboutgdip02\_art10")  
  
 Die vier Splines in der obigen Abbildung weisen im Anfangspunkt die gleiche Tangente auf.  Die Tangente ist die Linie, die vom Anfangspunkt zum nächsten Kurvenpunkt gezogen wird.  Entsprechend ist die gemeinsame Tangente am Endpunkt der Kurve die Linie, die vom Endpunkt zum vorherigen Kurvenpunkt gezogen wird.  
  
 Zum Zeichnen eines kardinalen Splines benötigen Sie eine Instanz der <xref:System.Drawing.Graphics>\-Klasse, <xref:System.Drawing.Pen> und ein Array von <xref:System.Drawing.Point>\-Objekten. Die Instanz der <xref:System.Drawing.Graphics>\-Klasse stellt die <xref:System.Drawing.Graphics.DrawCurve%2A>\-Methode bereit, durch die der Spline gezeichnet wird. Zum Speichern der Splineattribute, wie Linienstärke und \-farbe, wird <xref:System.Drawing.Pen> verwendet.  Im <xref:System.Drawing.Point>\-Objektarray werden die Punkte gespeichert, durch die die Kurve verläuft.  Das folgende Codebeispiel veranschaulicht, wie ein kardinaler Spline gezeichnet wird, der durch die Punkte in  `myPointArray` verläuft.  Der dritte Parameter ist die Spannung.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## Siehe auch  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)