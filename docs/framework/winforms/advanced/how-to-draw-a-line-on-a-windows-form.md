---
title: "Gewusst wie: Zeichnen einer Linie in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Graphics.DrawLine"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zeichnen von Linien"
  - "Zeichnen, Linien"
  - "Beispiele [Windows Forms], Zeichnen von Linien auf Formularen"
  - "Linien, Zeichnen"
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Zeichnen einer Linie in Windows&#160;Forms
In diesem Beispiel wird in einem Formular eine Linie gezeichnet.  Wenn Sie auf einem Formular zeichnen, behandeln Sie normalerweise das <xref:System.Windows.Forms.Control.Paint>\-Ereignis des Formulars und führen den Zeichnungsvorgang mithilfe der <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>\-Eigenschaft des <xref:System.Windows.Forms.PaintEventArgs> aus, wie in diesem Beispiel gezeigt.  
  
## Beispiel  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Robuste Programmierung  
 Für Objekte, die Systemressourcen beanspruchen, z. B. <xref:System.Drawing.Pen>\-Objekte, sollten Sie stets <xref:System.IDisposable.Dispose%2A> aufrufen.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics.DrawLine%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)