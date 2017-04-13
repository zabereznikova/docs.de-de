---
title: "Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Rechtecken | Microsoft Docs"
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
  - "Stifte, Zeichnen von Rechtecken"
  - "Rechtecke, Zeichnen"
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Rechtecken
Um Rechtecke zu zeichnen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt und ein <xref:System.Drawing.Pen>\-Objekt.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die <xref:System.Drawing.Graphics.DrawRectangle%2A>\-Methode bereit, und das <xref:System.Drawing.Pen>\-Objekt speichert Attribute der Linie, z. B. Farbe und Breite.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Rechteck gezeichnet, dessen obere linke Ecke die Koordinaten \(10, 10\) hat.  Das Rechteck weist eine Breite von 100 und eine Höhe von 50 auf.  Durch das an den <xref:System.Drawing.Pen.%23ctor%2A>\-Konstruktor übergebene zweite Argument wird angegeben, dass die Stiftbreite 5 Pixel beträgt.  
  
 Nach dem Zeichnen wird der Stift auf der Begrenzung des Rechtecks zentriert.  Da die Stiftbreite 5 Pixel beträgt, werden die Seiten des Rechtecks mit einer Breite von 5 Pixel gezeichnet, die sich wie folgt verteilen: 1 Pixel für die Begrenzung selbst, 2 Pixel für die Innenseite und 2 Pixel für die Außenseite.  Weitere Informationen zur Stiftausrichtung finden Sie unter [Gewusst wie: Festlegen von Stiftbreite und \-ausrichtung](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).  
  
 In der folgenden Abbildung ist das Rechteck dargestellt, das sich daraus ergibt.  Die punktierten Linien zeigen an, an welcher Stelle das Rechteck gezeichnet worden wäre, wenn die Stiftbreite 1 Pixel betragen hätte.  Die vergrößerte Ansicht der oberen linken Ecke des Rechtecks zeigt, dass die dicken schwarzen Linien auf diesen punktierten Linien zentriert sind.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens1.png "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)