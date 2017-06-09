---
title: "Gewusst wie: Zeichnen eines einzelnen B&#233;zier-Splines | Microsoft Docs"
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
  - "Béziersplinekurven, Zeichnen"
  - "Zeichnen, Béziersplinekurven"
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Zeichnen eines einzelnen B&#233;zier-Splines
Ein Bézier\-Spline wird durch vier Punkte definiert: einen Anfangspunkt, zwei Orientierungspunkte und einen Endpunkt.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Bézier\-Spline mit dem Anfangspunkt \(10, 100\) und dem Endpunkt \(200, 100\) gezeichnet.  Die Orientierungspunkte sind \(100, 10\) und \(150, 150\).  
  
 Die folgende Abbildung zeigt den resultierenden Bézier\-Spline mit Anfangspunkt, Orientierungspunkten und Endpunkt.  Die Abbildung zeigt auch die konvexe Hülle der Kurve. Dabei handelt es sich um ein Polygon, das entsteht, wenn die vier Punkte mit geraden Linien verbunden werden.  
  
 ![Bézier&#45;Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics.DrawBezier%2A>   
 [Bézier\-Splines in GDI\+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [Gewusst wie: Zeichnen einer Folge von Bézier\-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)