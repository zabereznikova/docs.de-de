---
title: "Gewusst wie: Verschieben von Bildfarben | Microsoft Docs"
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
  - "Bitmaps [Windows Forms], Ändern der Farben"
  - "Bildfarben [Windows Forms]"
  - "Bilder [Windows Forms], Ändern der Farben"
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Verschieben von Bildfarben
Durch die Verschiebung wird einem oder mehreren der vier Farbanteile ein Wert hinzuaddiert.  In der folgenden Tabelle sind die Farbmatrixeinträge aufgeführt, die Verschiebungen darstellen.  
  
|Zu verschiebende Komponente|Matrixeintrag|  
|---------------------------------|-------------------|  
|Rot|\[4\]\[0\]|  
|Grün|\[4\]\[1\]|  
|Blau|\[4\]\[2\]|  
|Alpha|\[4\]\[3\]|  
  
## Beispiel  
 Im folgenden Beispiel wird aus der Datei ColorBars.bmp ein <xref:System.Drawing.Image>\-Objekt erstellt.  Anschließend wird der Rotanteil jedes Bildpixels um den Wert 0,75 vergrößert.  Das ursprüngliche Bild wird längsseits des transformierten Bildes gezeichnet.  
  
 In der folgenden Abbildung ist das ursprüngliche Bild auf der linken und das transformierte Bild auf der rechten Seite zu sehen.  
  
 ![Verschieben von Farben](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 In der folgenden Tabelle sind die Farbvektoren für die vier Balken vor und nach der Rotverschiebung aufgelistet.  Da der Maximalwert für einen Farbanteil 1 beträgt, sollten Sie beachten, dass der Rotanteil in der zweiten Zeile nicht geändert wird.  \(Der Minimalwert für einen Farbanteil lautet entsprechend dazu 0.\)  
  
|Ursprünglich|Verschiebung|  
|------------------|------------------|  
|Schwarz \(0, 0, 0, 1\)|\(0.75, 0, 0, 1\)|  
|Rot \(1, 0, 0, 1\)|\(1, 0, 0, 1\)|  
|Grün \(0, 1, 0, 1\)|\(0.75, 1, 0, 1\)|  
|Blau \(0, 0, 1, 1\)|\(0.75, 0, 1, 1\)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Ersetzen Sie `ColorBars.bmp`  durch einen im System gültigen Bilddateinamen und \-pfad.  
  
## Siehe auch  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Neueinfärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)