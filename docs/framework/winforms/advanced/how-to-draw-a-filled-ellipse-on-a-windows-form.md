---
title: "Gewusst wie: Zeichnen einer ausgef&#252;llten Ellipse in Windows&#160;Forms | Microsoft Docs"
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
  - "Graphics.FillEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kreise, Zeichnen"
  - "Kreisformen"
  - "Zeichnen, Ellipsen"
  - "Ellipsen, Zeichnen"
  - "Formulare, Zeichnen von Ellipsen"
  - "Formen, Zeichnen"
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zeichnen einer ausgef&#252;llten Ellipse in Windows&#160;Forms
In diesem Beispiel wird in einem Formular eine ausgefüllte Ellipse gezeichnet.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
 Sie können diese Methode nicht im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler aufrufen.  Der gezeichnete Inhalt wird nicht neu gezeichnet, wenn die Größe des Formulars geändert oder das Formular durch ein anderes Formular verdeckt wird.  Wenn der Inhalt automatisch neu gezeichnet werden soll, müssen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschreiben.  
  
## Robuste Programmierung  
 Sie sollten immer <xref:System.IDisposable.Dispose%2A> für Objekte aufrufen, die Systemressourcen beanspruchen, z. B. die Objekte <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics>.  
  
## Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)