---
title: "Verwenden eines Pinsels f&#252;r Farbverl&#228;ufe zum Ausf&#252;llen von Formen | Microsoft Docs"
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
  - "Pinsel, Farbverlaufspinsel"
  - "Beispiele [Windows Forms], Farbverlaufspinsel"
  - "Farbverlaufspinsel"
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Verwenden eines Pinsels f&#252;r Farbverl&#228;ufe zum Ausf&#252;llen von Formen
Sie können einen Farbverlaufspinsel verwenden, um eine Form mit einem graduellen Farbwechsel auszufüllen.  Beispielsweise können Sie einen horizontalen Farbverlauf verwenden, um eine Form mit einer Farbe auszufüllen, die sich innerhalb der Form graduell von links nach rechts ändert.  Stellen Sie sich ein Rechteck vor, dessen linke Seite schwarz \(Rot\-, Grün\- und Blauanteil 0, 0, 0\) und dessen rechte Seite rot ist \(255, 0, 0\).  Wenn das Rechteck 256 Pixel breit ist, ist der Rotanteil eines bestimmten Pixels um 1 höher als der Rotanteil des Pixels unmittelbar links davon.  Das in einer Zeile ganz links liegende Pixel hat die Farbanteile \(0, 0, 0\), das zweite Pixel die Farbanteile \(1, 0, 0\), das dritte Pixel die Farbanteile \(2, 0, 0\) usw., bis zum ganz rechts liegenden Pixel mit den Farbanteilen \(255, 0, 0\).  Diese interpolierten Farbwerte machen den Farbverlauf aus.  
  
 In einem linearen Farbverlauf wird die Farbe horizontal, vertikal oder entlang einer diagonalen Linie geändert.  Bei einem Pfadfarbverlauf wird die Farbe im Innenbereich und entlang der Begrenzung eines Pfades geändert.  Durch Anpassen von Pfadfarbverläufen können Sie eine große Vielfalt von Effekten erzielen.  
  
 In der folgenden Abbildung wird ein Rechteck gezeigt, das mit einem Pinsel für lineare Verläufe ausgefüllt wurde, und eine Ellipse, die mit einem Pinsel für Pfadfarbverläufe ausgefüllt wurde.  
  
 ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen eines linearen Farbverlaufs](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 Zeigt, wie ein linearer Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.LinearGradientBrush>\-Klasse erstellt wird.  
  
 [Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 Beschreibt, wie ein Pfadfarbverlauf mithilfe der <xref:System.Drawing.Drawing2D.PathGradientBrush>\-Klasse erstellt wird.  
  
 [Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 Erläutert, wie die Gammakorrektur mit einem Farbverlaufspinsel verwendet wird.  
  
## Referenz  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>  
 Enthält eine Beschreibung dieser Klasse sowie Links zu allen zugehörigen Membern.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=fullName>  
 Enthält eine Beschreibung dieser Klasse sowie Links zu allen zugehörigen Membern.