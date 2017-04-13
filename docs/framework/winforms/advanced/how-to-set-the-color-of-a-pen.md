---
title: "Gewusst wie: Festlegen der Farbe eines Stiftes | Microsoft Docs"
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
  - "Farbstifte"
  - "Stifte, Festlegen der Farbe"
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen der Farbe eines Stiftes
In diesem Beispiel wird die Farbe eines bereits vorhandenen <xref:System.Drawing.Pen>\-Objekts geändert.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Drawing.Pen>\-Objekt mit dem Namen  `myPen` muss vorhanden sein.  
  
## Robuste Programmierung  
 Nachdem die Arbeit mit Objekten beendet wurde, sollten Sie <xref:System.Drawing.Pen.Dispose%2A> für die Objekte aufrufen, die Systemressourcen beanspruchen \(z. B. <xref:System.Drawing.Pen>\-Objekte\).  
  
## Siehe auch  
 <xref:System.Drawing.Pen>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Gewusst wie: Erstellen eines Stiftes](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Stifte, Linien und Rechtecke in GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)