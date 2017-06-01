---
title: "Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Linien | Microsoft Docs"
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
  - "Linien, Zeichnen"
  - "Stifte, Zeichnen von Linien"
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Linien
Um Linien zu zeichnen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt und ein <xref:System.Drawing.Pen>\-Objekt.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode bereit, und das <xref:System.Drawing.Pen>\-Objekt speichert Attribute der Linie, z. B. Farbe und Breite.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Linie zwischen den Punkten \(20, 10\) und \(300, 100\) gezeichnet.  Die erste Anweisung verwendet den <xref:System.Drawing.Pen.%23ctor%2A>\-Klassenkonstruktor, um einen schwarzen Stift zu erstellen.  Das an den <xref:System.Drawing.Pen.%23ctor%2A>\-Konstruktor übergebene Argument ist ein mit der <xref:System.Drawing.Color.FromArgb%2A>\-Methode erstelltes <xref:System.Drawing.Color>\-Objekt.  Die zum Erstellen des <xref:System.Drawing.Color>\-Objekts verwendeten Werte – \(255, 0, 0, 0\) – entsprechen dem Alpha\-, Rot\-, Grün\- und Blauanteil der Farbe.  Durch diese Werte wird ein nicht transparenter schwarzer Stift definiert.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 <xref:System.Drawing.Pen>   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Stifte, Linien und Rechtecke in GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)