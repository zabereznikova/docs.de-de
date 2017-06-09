---
title: "Gewusst wie: Drehen von Farben | Microsoft Docs"
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
  - "Farben, Drehen"
  - "Beispiele [Windows Forms], Drehen von Farben"
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Drehen von Farben
Die Drehung in einem vierdimensionalen Farbraum ist schwer zu visualisieren.  Sie ist jedoch leichter vorstellbar, wenn vereinbart wird, dass ein Farbanteil stets einen festen Wert beibehält.  Angenommen, der Alphaanteil behält einen festen Wert von 1 \(vollständig deckend\) bei.  In diesem Fall lässt sich ein dreidimensionaler Farbraum mit Rot\-, Grün\- und Blauachsen, wie in der folgenden Abbildung, einfach visualisieren.  
  
 ![Neueinfärbung](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Eine Farbe kann man sich im 3D\-Raum wie einen Punkt vorstellen.  Der Punkt \(1, 0, 0\) stellt im Raum beispielsweise die Farbe Rot und der Punkt \(0, 1, 0\) die Farbe Grün dar.  
  
 Die folgende Abbildung veranschaulicht, welche Auswirkungen die Drehung der Farbe \(1, 0, 0\) in einem Winkel von 60 Grad in der Rot\-Grün\-Ebene hat.  Die Drehung in einer Ebene parallel zur Rot\-Grün\-Ebene können Sie sich wie eine Drehung um die Blauachse vorstellen.  
  
 ![Neueinfärbung](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 In der folgenden Abbildung wird veranschaulicht, wie Sie eine Farbmatrix initialisieren, um Drehungen um jede der drei Koordinatenachsen \(Rot, Grün, Blau\) auszuführen.  
  
 ![Neueinfärbung](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## Beispiel  
 Im folgenden Beispiel wird eine 60\-Grad\-Drehung um die Blauachse auf ein komplett einfarbiges Bild \(1, 0, 0.6\) angewendet.  In einer Ebene, die parallel zur Rot\-Grün\-Ebene verläuft, wird der Drehwinkel aufgehoben.  
  
 In der folgenden Abbildung ist das ursprüngliche Bild auf der linken und das Bild, dessen Farben gedreht wurden, auf der rechten Seite zu sehen.  
  
 ![Drehen von Farben](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 In der folgenden Abbildung wird die im nachstehenden Code ausgeführte Farbdrehung veranschaulicht.  
  
 ![Neueinfärbung](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Ersetzen Sie `RotationInput.bmp` durch einen für das System gültigen Dateinamen und Pfad.  
  
## Siehe auch  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Neueinfärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)