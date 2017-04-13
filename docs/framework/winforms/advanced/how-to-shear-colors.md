---
title: "Gewusst wie: Scheren von Farben | Microsoft Docs"
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
  - "Farben, Scheren"
  - "Farben, Transformieren mit Farbmatrizen"
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Scheren von Farben
Beim Scheren wird ein Farbanteil um einen Wert verringert oder erhöht, der sich proportional zu einem anderen Farbanteil verhält.  Beachten Sie beispielsweise die Transformation, bei der der Rotanteil um die Hälfte des Werts des Blauanteils vergrößert wird.  Bei einer solchen Transformation würde die Farbe \(0.2, 0.5, 1\) zu \(0.7, 0.5, 1\) werden.  Der Wert des neuen Rotanteils ergibt sich aus 0.2 \+ \(1\/2\)\(1\) \= 0.7.  
  
## Beispiel  
 Im folgenden Beispiel wird aus der Datei ColorBars4.bmp ein <xref:System.Drawing.Image>\-Objekt erstellt.  Anschließend wird im Code die im vorangehenden Abschnitt erläuterte Schertransformation auf jedes Bildpixel angewendet.  
  
 In der folgenden Abbildung ist das ursprüngliche Bild auf der linken und das Bild mit der Schertransformation auf der rechten Seite zu sehen.  
  
 ![Scheren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 In der folgenden Tabelle sind die Farbvektoren für die vier Balken vor und nach der Schertransformation aufgelistet.  
  
|Ursprünglich|Schertransformation|  
|------------------|-------------------------|  
|\(0, 0, 1, 1\)|\(0.5, 0, 1, 1\)|  
|\(0.5, 1, 0.5, 1\)|\(0.75, 1, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(1, 1, 0, 1\)|  
|\(0.4, 0.4, 0.4, 1\)|\(0.6, 0.4, 0.4, 1\)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Ersetzen Sie `ColorBars.bmp` durch einen für das System gültigen Bildnamen und Pfad.  
  
## Siehe auch  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Neueinfärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)