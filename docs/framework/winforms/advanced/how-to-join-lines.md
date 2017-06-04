---
title: "Gewusst wie: Verkn&#252;pfen von Linien | Microsoft Docs"
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
  - "Abgeschrägt (Linienverbindungsstil)"
  - "Zeichnen, Verbinden von Linien"
  - "Grafiken, Verbinden von Linien"
  - "GraphicsPath-Objekt"
  - "Linienverbindung"
  - "Linien, Verknüpfen"
  - "Spitz zulaufend (Linienverbindungsstil)"
  - "Pen-Klasse"
  - "Abgerundet (Linienverbindungsstil)"
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verkn&#252;pfen von Linien
Eine Linienverbindung ist der Punkt, an dem zwei Linien aufeinander treffen oder sich schneiden.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet drei Linienverbindungsstile: Winkel, Schräge Kante und Rund.  Der Linienverbindungsstil ist eine Eigenschaft der <xref:System.Drawing.Pen>\-Klasse.  Wenn Sie einen Linienverbindungsstil für ein <xref:System.Drawing.Pen>\-Objekt festlegen, wird dieser Verbindungsstil für alle verbundenen Linien in sämtlichen <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekten übernommen, die mit diesem Stift gezeichnet wurden.  
  
 Die folgende Abbildung zeigt das Ergebnis des Beispiels für eine abgeschrägte Linienverbindung.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens5.png "pens5")  
  
## Beispiel  
 Sie können den Linienverbindungsstil über die <xref:System.Drawing.Pen.LineJoin%2A>\-Eigenschaft der <xref:System.Drawing.Pen>\-Klasse festlegen.  Das Beispiel veranschaulicht, wie eine horizontale und eine vertikale Linie mit einer abgeschrägten Linienverbindung versehen werden.  Der der <xref:System.Drawing.Pen.LineJoin%2A>\-Eigenschaft zugewiesene <xref:System.Drawing.Drawing2D.LineJoin>\-Wert entspricht im folgenden Code einem Member der <xref:System.Drawing.Drawing2D.LineJoin>\-Enumeration.  Die anderen Member der <xref:System.Drawing.Drawing2D.LineJoin>\-Enumeration lauten <xref:System.Drawing.Drawing2D.LineJoin> und <xref:System.Drawing.Drawing2D.LineJoin>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)