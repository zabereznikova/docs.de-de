---
title: "Windows Forms-Koordinaten | Microsoft Docs"
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
  - "Clientkoordinaten"
  - "Koordinaten, Windows Forms"
  - "Bildschirmkoordinaten"
  - "Windows Forms-Koordinaten"
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Windows Forms-Koordinaten
Das Koordinatensystem für ein Windows Form basiert auf Gerätekoordinaten, und die grundlegende Maßeinheit beim Zeichnen in Windows Forms ist die Geräteeinheit \(normalerweise Pixel\).  Punkte auf dem Bildschirm werden durch X\- und Y\-Koordinatenpaare beschrieben, wobei die X\-Koordinaten nach rechts zunehmen und die Y\-Koordinaten von oben nach unten.  Die Position des Ursprungs relativ zum Bildschirm hängt davon ab, ob Sie Bildschirm\- oder Clientkoordinaten angeben.  
  
## Bildschirmkoordinaten  
 Eine Windows Forms\-Anwendung gibt die Position eines Fensters auf dem Bildschirm in Bildschirmkoordinaten an.  Für Bildschirmkoordinaten ist der Ursprung die linke obere Ecke des Bildschirms.  Die vollständige Position eines Fensters wird häufig von einer <xref:System.Drawing.Rectangle>\-Struktur beschrieben, die die Bildschirmkoordinaten von zwei Punkten enthält, die wiederum die obere linke und untere rechte Ecke des Fensters definieren.  
  
## Clientkoordinaten  
 Eine Windows Forms\-Anwendung gibt die Position von Punkten in einem Formular oder Steuerelement mithilfe von Clientkoordinaten an.  Der Ursprung für Clientkoordinaten ist die obere linke Ecke des Clientbereichs des Steuerelements oder Formulars.  Clientkoordinaten gewährleisten, dass eine Anwendung beim Zeichnen in einem Formular oder Steuerelement konsistente Koordinatenwerte verwenden kann, unabhängig von der Position des Formulars oder Steuerelements auf dem Bildschirm.  
  
 Die Maße des Clientbereichs werden ebenfalls von einer <xref:System.Drawing.Rectangle>\-Struktur beschrieben, die Clientkoordinaten für den Bereich enthält.  In allen Fällen ist die obere linke Koordinate des Rechtecks in den Clientbereich eingeschlossen, während die untere rechte Koordinate ausgeschlossen ist.  Grafikoperationen schließen den rechten und unteren Rand eines Clientbereichs nicht ein.  Mit der <xref:System.Drawing.Graphics.FillRectangle%2A>\-Methode wird ein festgelegtes Rechteck bis zum rechten und unteren Rand gefüllt, die Kanten selbst werden jedoch nicht eingeschlossen.  
  
## Zuordnen von einem Koordinatentyp zu einem anderen  
 Gelegentlich müssen Sie Bildschirmkoordinaten Clientkoordinaten zuordnen.  Eine einfache Möglichkeit hierzu bieten die <xref:System.Windows.Forms.Control.PointToClient%2A>\-Methode und die <xref:System.Windows.Forms.Control.PointToScreen%2A>\-Methode der <xref:System.Windows.Forms.Control>\-Klasse.  Beispielsweise wird die <xref:System.Windows.Forms.Control.MousePosition%2A>\-Eigenschaft von <xref:System.Windows.Forms.Control> in Bildschirmkoordinaten angegeben, Sie möchten diese jedoch in Clientkoordinaten konvertieren.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.PointToClient%2A>   
 <xref:System.Windows.Forms.Control.PointToScreen%2A>