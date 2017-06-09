---
title: "Alphablending von Linien und F&#252;llungen | Microsoft Docs"
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
  - "Alphablending"
  - "Alphablending, Verwenden mit Füllungen"
  - "Alphablending, Verwenden mit Linien"
  - "Beispiele [Windows Forms], Alphablending"
  - "Füllungen, Alphablending"
  - "Linien, Hinzufügen von Transparenz"
  - "Linien, Alphablending"
  - "Formen, Hinzufügen von Transparenz"
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Alphablending von Linien und F&#252;llungen
In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] entspricht eine Farbe einem 32\-Bit\-Wert mit jeweils 8 Bit für Alpha, Rot, Grün und Blau.  Der Alphawert gibt die Transparenz der Farbe an, also das Mischverhältnis der Farbe mit der Hintergrundfarbe.  Alphawerte reichen von 0 bis 255. Der Wert 0 steht für eine voll transparente und 255 für eine vollständig deckende Farbe.  
  
 Beim Alphablending werden die Farbdaten von Quelle und Hintergrund pixelweise gemischt.  Jeder der drei Anteile \(Rot, Grün, Blau\) einer bestimmten Quellfarbe wird entsprechend der folgenden Formel mit dem entsprechenden Anteil der Hintergrundfarbe gemischt:  
  
 Anzeigefarbe \= Quellfarbe × Alpha \/ 255 \+ Hintergrundfarbe × \(255 \- Alpha\) \/ 255  
  
 Angenommen, der Rotanteil der Quellfarbe entspricht dem Wert 150 und der Rotanteil der Hintergrundfarbe dem Wert 100.  Wenn der Alphawert bei 200 liegt, wird der Rotanteil der sich ergebenden Farbe wie folgt berechnet:  
  
 150 × 200 \/ 255 \+ 100 × \(255 – 200\) \/ 255 \= 139  
  
## In diesem Abschnitt  
 [Gewusst wie: Zeichnen deckender und halbtransparenter Linien](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 Zeigt an, wie Alphablending\-Zeilen gezeichnet werden.  
  
 [Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Erläutert das Alphablending mit Pinseln.  
  
 [Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Beschreibt, wie Alphablending mit dem <xref:System.Drawing.Drawing2D.CompositingMode> gesteuert wird.  
  
 [Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Erklärt, wie ein <xref:System.Drawing.Imaging.ColorMatrix>\-Objekt verwendet wird, um Alphablending zu steuern.