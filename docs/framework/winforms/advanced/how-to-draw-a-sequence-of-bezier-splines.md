---
title: "Gewusst wie: Zeichnen einer Folge von B&#233;zier-Splines | Microsoft Docs"
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
  - "Béziersplinekurven, Zeichnen einer Sequenz von"
  - "Splines, Zeichnen von Bézier"
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Zeichnen einer Folge von B&#233;zier-Splines
Mithilfe der <xref:System.Drawing.Graphics.DrawBeziers%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse können Sie eine Folge verbundener Bézier\-Splines zeichnen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Kurve gezeichnet, die aus zwei miteinander verbundenen Bézier\-Splines besteht.  Der Endpunkt des ersten Bézier\-Splines ist gleichzeitig der Anfangspunkt des zweiten Bézier\-Splines.  
  
 In der folgenden Abbildung sind die miteinander verbundenen Splines mit den sieben Punkten dargestellt.  
  
 ![Bézier&#45;Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Bézier\-Splines in GDI\+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)