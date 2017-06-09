---
title: "Skalieren von Farben mithilfe von Transformationen | Microsoft Docs"
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
  - "Farben, Skalieren"
  - "Transformationen, Zum Skalieren von Farben"
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Skalieren von Farben mithilfe von Transformationen
Durch die Skalierungstransformation wird einer oder mehrere der vier Farbanteile mit einer Zahl multipliziert.  In der folgenden Tabelle sind die Farbmatrixeinträge aufgeführt, die eine Skalierung darstellen.  
  
|Zu skalierende Komponente|Matrixeintrag|  
|-------------------------------|-------------------|  
|Rot|\[0\]\[0\]|  
|Grün|\[1\]\[1\]|  
|Blau|\[2\]\[2\]|  
|Alpha|\[3\]\[3\]|  
  
## Skalieren einer Farbe  
 Im folgenden Beispiel wird aus der Datei ColorBars2.bmp ein <xref:System.Drawing.Image>\-Objekt erstellt.  Anschließend skaliert der Code den Blauanteil jedes Bildpixels mit dem Faktor 2.  Das ursprüngliche Bild wird längsseits des transformierten Bildes gezeichnet.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 In der folgenden Abbildung ist das ursprüngliche Bild auf der linken und das skalierte Bild auf der rechten Seite zu sehen.  
  
 ![Skalieren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 In der folgenden Tabelle sind die Farbvektoren für die vier Balken vor und nach der Blauskalierung aufgelistet.  Beachten Sie, dass der Blauanteil im vierten Farbbalken von 0.8 auf 0.6 verringert wurde.  Dies liegt daran, dass in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] lediglich die Nachkommastellen des Ergebnisses berücksichtigt werden.  Beispiel: \(2\)\(0.8\) \= 1.6, und die Nachkommastelle von 1.6 ist 0.6.  Indem nur die Nachkommastellen beibehalten werden, ist gewährleistet, dass sich das Ergebnis immer im Intervall \[0, 1\] befindet.  
  
|Ursprünglich|Skalierung|  
|------------------|----------------|  
|\(0.4, 0.4, 0.4, 1\)|\(0.4, 0.4, 0.8, 1\)|  
|\(0.4, 0.2, 0.2, 1\)|\(0.4, 0.2, 0.4, 1\)|  
|\(0.2, 0.4, 0.2, 1\)|\(0.2, 0.4, 0.4, 1\)|  
|\(0.4, 0.4, 0.8, 1\)|\(0.4, 0.4, 0.6, 1\)|  
  
## Skalieren mehrerer Farben  
 Im folgenden Beispiel wird aus der Datei ColorBars2.bmp ein <xref:System.Drawing.Image>\-Objekt erstellt.  Anschließend wird durch den Code der Rot\-, Grün\- und Blauanteil jedes Bildpixels skaliert.  Die Skalierung hat folgendes Ergebnis: Die Rotanteile werden um 25 Prozent, die Grünanteile um 35 Prozent und die Blauanteile um 50 Prozent herabgestuft.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 In der folgenden Abbildung ist das ursprüngliche Bild auf der linken und das skalierte Bild auf der rechten Seite zu sehen.  
  
 ![Skalieren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 In der folgenden Tabelle sind die Farbvektoren für die vier Balken vor und nach der Rot\-, Grün\- und Blauskalierung aufgelistet.  
  
|Ursprünglich|Skalierung|  
|------------------|----------------|  
|\(0.6, 0.6, 0.6, 1\)|\(0.45, 0.39, 0.3, 1\)|  
|\(0, 1, 1, 1\)|\(0, 0.65, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(0.75, 0.65, 0, 1\)|  
|\(1, 0, 1, 1\)|\(0.75, 0, 0.5, 1\)|  
  
## Siehe auch  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Neueinfärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)