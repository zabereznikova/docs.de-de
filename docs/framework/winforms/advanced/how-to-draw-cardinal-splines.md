---
title: "Gewusst wie: Zeichnen von kardinalen Splines | Microsoft Docs"
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
  - "Kardinale Splinekurven, Zeichnen"
  - "Zeichnen, Kardinale Splinekurven"
  - "Grafiken, Kardinale Splinekurven"
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Zeichnen von kardinalen Splines
Bei einem kardinalen Spline handelt es sich um eine Kurve, die glatt durch eine vorgegebene Anzahl von Punkten verläuft.  Um einen kardinalen Spline zu zeichnen, erstellen Sie ein <xref:System.Drawing.Graphics>\-Objekt und übergeben die Adresse eines Punktearrays an die <xref:System.Drawing.Graphics.DrawCurve%2A>\-Methode.  
  
### Zeichnen eines glockenförmigen kardinalen Splines  
  
-   Im folgenden Beispiel wird ein glockenförmiger kardinaler Spline gezeichnet, der durch fünf vorgegebene Punkte verläuft.  In der folgenden Abbildung sind die Kurve und die fünf Punkte dargestellt.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### Zeichnen eines geschlossenen kardinalen Splines  
  
-   Verwenden Sie die <xref:System.Drawing.Graphics.DrawClosedCurve%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse, um einen geschlossenen kardinalen Spline zu zeichnen.  In einem geschlossenen kardinalen Spline wird die Kurve über den letzten Punkt im Array hinaus fortgesetzt; dieser wird mit dem ersten Punkt im Array verbunden.  Im folgenden Beispiel wird ein geschlossener kardinaler Spline gezeichnet, der durch sechs vorgegebene Punkte verläuft.  In der folgenden Abbildung ist der geschlossene Spline mit seinen sechs Punkten dargestellt.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### Ändern der Krümmung eines kardinalen Splines  
  
-   Ändern Sie die Krümmung eines kardinalen Splines, indem Sie ein Spannungsargument an die <xref:System.Drawing.Graphics.DrawCurve%2A>\-Methode übergeben.  Im folgenden Beispiel werden drei kardinale Splines gezeichnet, die durch dieselben Punkte verlaufen.  In der folgenden Abbildung sind die drei Splinekurven mit den entsprechenden Spannungswerten dargestellt.  Wenn die Spannung gleich 0 ist, werden die Punkte durch gerade Linien verbunden.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## Kompilieren des Codes  
 Die vorangehenden Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)