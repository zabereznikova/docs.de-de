---
title: "Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen | Microsoft Docs"
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
  - "Figuren, Erstellen aus Linien"
  - "Figuren, Erstellen aus Formen"
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen
Um eine Figur zu erstellen, legen Sie zunächst einen <xref:System.Drawing.Drawing2D.GraphicsPath> an und fügen dem Pfad anschließend durch Aufrufen von Methoden, wie z. B. <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> oder <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, Grundelemente hinzu.  
  
## Beispiel  
 Die folgenden Codebeispiele erstellen Pfade, die Figuren enthalten:  
  
-   Im ersten Beispiel wird ein Pfad erstellt, der eine einzelne Figur enthält.  Die Figur besteht aus einem einzelnen Bogen.  Der Bogen hat einen Krümmungswinkel von \-180 Grad, d. h., im Standardkoordinatensystem verläuft er entgegen dem Uhrzeigersinn.  
  
-   Im zweiten Beispiel wird ein Pfad erstellt, der aus zwei Figuren besteht.  Die erste Figur ist ein Bogen, auf den eine Linie folgt.  Die zweite Figur besteht aus einer Linie, auf die eine Kurve und eine weitere Linie folgt.  Die erste Figur wird offen gelassen, und die zweite ist geschlossen.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## Kompilieren des Codes  
 Die vorangehenden Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, wobei es sich um einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers handelt.  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)