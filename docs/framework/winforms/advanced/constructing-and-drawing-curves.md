---
title: "Erstellen und Zeichnen von Kurven | Microsoft Docs"
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
  - "Kurven, Zeichnen"
  - "Zeichnen, Kurven"
  - "Beispiele [Windows Forms], Zeichnen von Kurven"
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Erstellen und Zeichnen von Kurven
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] unterstützt mehrere Typen von Kurven: Ellipsen, Bögen, kardinale Splines und Bézier\-Splines.  Eine Ellipse wird durch das umschließende Rechteck definiert; ein Bogen ist ein Teil einer Ellipse, der durch einen Anfangswinkel und einen Krümmungswinkel definiert wird.  Kardinale Splines werden durch ein Array von Punkten und einen Spannungsparameter definiert. Die geglättete Kurve verläuft durch jeden Punkt im Array, und der Spannungsparameter beeinflusst die Krümmung der Kurve.  Bézier\-Splines sind durch zwei Endpunkte und zwei Kontrollpunkte definiert. Die Kurve verläuft zwar nicht durch die Kontrollpunkte, diese beeinflussen aber die Richtung und Krümmung der Kurve von einem Endpunkt zum anderen.  
  
## In diesem Abschnitt  
 [Gewusst wie: Zeichnen von kardinalen Splines](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 Beschreibt kardinale Splines und wie sie gezeichnet werden.  
  
 [Gewusst wie: Zeichnen eines einzelnen Bézier\-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 Beschreibt Bézier\-Splines und wie sie gezeichnet werden.  
  
 [Gewusst wie: Zeichnen einer Folge von Bézier\-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 Erklärt, wie mehrere Bézier\-Splines nacheinander gezeichnet werden.