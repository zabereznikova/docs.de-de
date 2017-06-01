---
title: "Drei Kategorien von Grafikdiensten | Microsoft Docs"
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
  - "2D-Vektorgrafiken"
  - "Grafiken, Kategorien"
  - "Imaging"
  - "Typografie"
  - "Vektorgrafiken"
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Drei Kategorien von Grafikdiensten
Die Grafikdienste in Windows Forms können in folgende drei breit gefasste Kategorien eingeteilt werden:  
  
-   Zweidimensionale \(2D\)\-Vektorgrafiken  
  
-   Imaging  
  
-   Typografie  
  
## 2D‑Vektorgrafik  
 Zweidimensionale Vektorgrafiken sind Grundelemente \(z. B. Linien, Kurven und Figuren\), die durch Punkte in einem Koordinatensystem angegeben werden.  So wird z. B. eine Gerade durch ihre beiden Endpunkte angegeben. Ein Rechteck wird durch einen Punkt, der die linke obere Ecke des Rechtecks angibt, und ein Zahlenpaar für Breite und Höhe definiert.  Ein einfacher Pfad wird als ein Array aus Punkten angegeben, die durch Geraden miteinander verbunden werden.  Ein Bézier\-Spline ist eine anspruchsvolle Kurve, die durch vier Steuerpunkte angegeben wird.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet Klassen und Strukturen, in denen Informationen über die eigentlichen Grundelemente gespeichert werden, Klassen, in denen gespeichert wird, wie die Grundelemente gezeichnet werden, und Klassen, die den Zeichenvorgang ausführen.  Beispielsweise werden in der <xref:System.Drawing.Rectangle>\-Struktur die Position und die Größe eines Rechtecks gespeichert. In der <xref:System.Drawing.Pen>\-Klasse werden Informationen über Linienfarbe, \-stärke und \-stil gespeichert. Die <xref:System.Drawing.Graphics>\-Klasse enthält Methoden zum Zeichnen von Linien, Rechtecken, Pfaden und anderen Formen.  Darüber hinaus gibt es mehrere <xref:System.Drawing.Brush>\-Klassen, in denen gespeichert wird, wie geschlossene Formen und Pfade mit Farben oder Mustern gefüllt werden.  
  
 Sie können ein Vektorbild, d. h. eine Folge von Grafikbefehlen, in einer Metadatei aufzeichnen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt die <xref:System.Drawing.Imaging.Metafile>\-Klasse zum Aufzeichnen, Anzeigen und Speichern von Metadateien bereit.  Mit der <xref:System.Drawing.Imaging.MetafileHeader>\-Klasse und der <xref:System.Drawing.Imaging.MetaHeader>\-Klasse können Sie die in einem Metadateiheader gespeicherten Daten überprüfen.  
  
## Imaging  
 Bestimmte Arten von Bildern können mit der Technik der Vektorgrafik nur schwer oder garnicht angezeigt werden.  So können z. B. die Bilder auf Symbolleisten\-Schaltflächen und die Bilder, die als Symbole angezeigt werden, nur schwer als Kombination aus Linien und Kurven wiedergegeben werden.  Eine hoch auflösende digitale Fotografie eines voll besetzten Fußballstadions ist mit der Vektortechnik sogar noch schwieriger zu erstellen.  Bilder dieses Typs werden als Bitmaps gespeichert, d. h. als Arrays aus Zahlen, die die Farben der einzelnen Punkte auf dem Bildschirm darstellen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt die <xref:System.Drawing.Bitmap>\-Klasse zum Anzeigen, Bearbeiten und Speichern von Bitmaps bereit.  
  
## Typografie  
 Unter Typografie versteht man die Anzeige von Text in einer Vielzahl von Schriftarten, \-graden und \-stilen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet umfassende Unterstützung für diese komplexen Aufgaben.  Eine der neuen Funktionen von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ist das Teilpixel\-Antialiasing, durch das ein Text, der auf einem LCD\-Bildschirm ausgegeben wird, ein glatteres Erscheinungsbild erhält.  
  
 Außerdem bietet Windows Forms die Möglichkeit, Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\-Funktionen in der <xref:System.Windows.Forms.TextRenderer>\-Klasse zu zeichnen.  
  
## Siehe auch  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [Verwalteter Code in GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)