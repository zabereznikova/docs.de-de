---
title: "Gewusst wie: Zeichnen einer Linie mit Linienenden | Microsoft Docs"
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
  - "Zeichnen von Linien, Linienenden"
  - "Zeichnen, Linien"
  - "Linien, Zeichnen"
  - "Stifte, Zeichnen von Linien"
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Zeichnen einer Linie mit Linienenden
Sie können den Anfang oder das Ende einer Linie in einer von mehreren Formen, so genannten Linienenden, zeichnen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] unterstützt verschiedene Linienenden, darunter abgerundete oder quadratische Linienenden bzw. Enden in Form einer Raute oder einer Pfeilspitze.  
  
## Beispiel  
 Sie können Linienenden für den Anfang einer Linie \(**StartCap**\), das Ende einer Linie \(**EndCap**\) oder die Striche einer gestrichelten Linie \(**DashCap**\) festlegen.  
  
 Im folgenden Beispiel wird eine Linie gezeichnet, die an einem Ende mit einer Pfeilspitze abschließt und am anderen Ende abgerundet ist.  In der Abbildung ist die resultierende Linie dargestellt:  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens4.png "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein Windows Form, und verarbeiten Sie das <xref:System.Windows.Forms.Control.Paint>\-Ereignis des Formulars.  Fügen Sie den Beispielcode in den <xref:System.Windows.Forms.Control.Paint>\-Ereignishandler ein, und übergeben Sie `e` als <xref:System.Windows.Forms.PaintEventArgs>.  
  
## Siehe auch  
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=fullName>   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)