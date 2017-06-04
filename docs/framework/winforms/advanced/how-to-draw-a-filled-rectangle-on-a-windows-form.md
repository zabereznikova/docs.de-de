---
title: "Gewusst wie: Zeichnen eines ausgef&#252;llten Rechtecks in Windows&#160;Forms | Microsoft Docs"
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
  - "Graphics.FillRectangle"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zeichnen von Rechtecken"
  - "Zeichnen, Rechtecke"
  - "Rechtecke, Zeichnen"
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Zeichnen eines ausgef&#252;llten Rechtecks in Windows&#160;Forms
In diesem Beispiel wird in einem Formular ein ausgefülltes Rechteck gezeichnet.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## Kompilieren des Codes  
 Sie können diese Methode nicht im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler aufrufen.  Der gezeichnete Inhalt wird nicht neu gezeichnet, wenn die Größe des Formulars geändert oder das Formular durch ein anderes Formular verdeckt wird.  Wenn der Inhalt automatisch neu gezeichnet werden soll, müssen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschreiben.  
  
## Robuste Programmierung  
 Sie sollten immer <xref:System.IDisposable.Dispose%2A> für Objekte aufrufen, die Systemressourcen beanspruchen, z. B. die Objekte <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics>.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics.FillRectangle%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Pinsel und gefüllte Formen in GDI\+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)