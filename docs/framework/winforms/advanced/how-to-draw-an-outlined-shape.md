---
title: "Gewusst wie: Zeichnen der Kontur einer Form | Microsoft Docs"
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
  - "Graphics.DrawEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kreise"
  - "Kreise, Zeichnen"
  - "Kreisformen"
  - "Zeichnen, Kreisformen"
  - "Zeichnen, Formen"
  - "Ellipsen, Zeichnen"
  - "Formulare, Zeichnen von Kreisformen"
  - "Konturen für Formen, Zeichnen"
  - "Konturen für Formen, Beispiele"
  - "Formen, Zeichnen"
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Zeichnen der Kontur einer Form
In diesem Beispiel werden in einem Formular Ellipsen und Rechtecke mit Rand gezeichnet.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## Kompilieren des Codes  
 Sie können diese Methode nicht im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler aufrufen.  Der gezeichnete Inhalt wird nicht neu gezeichnet, wenn die Größe des Formulars geändert oder das Formular durch ein anderes Formular verdeckt wird.  Wenn der Inhalt automatisch neu gezeichnet werden soll, müssen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschreiben.  
  
## Robuste Programmierung  
 Sie sollten für Objekte, die Systemressourcen beanspruchen \(z. B. das <xref:System.Drawing.Pen>\-Objekt und das <xref:System.Drawing.Graphics>\-Objekt\), immer <xref:System.IDisposable.Dispose%2A> aufrufen.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Graphics.DrawRectangle%2A>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)