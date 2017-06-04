---
title: "Gewusst wie: Abrufen von Schriftarteigenschaften | Microsoft Docs"
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
  - "Schriftarteigenschaften, Abrufen"
  - "Schriftarten, Abrufen der Eigenschaften"
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Abrufen von Schriftarteigenschaften
Die <xref:System.Drawing.FontFamily>\-Klasse bietet die folgenden Methoden zum Abrufen verschiedener Schriftarteigenschaften für eine bestimmte Kategorie\-\/Schriftschnittkombination:  
  
-   <xref:System.Drawing.FontFamily.GetEmHeight%2A>\(FontStyle\)  
  
-   <xref:System.Drawing.FontFamily.GetCellAscent%2A>\(FontStyle\)  
  
-   <xref:System.Drawing.FontFamily.GetCellDescent%2A>\(FontStyle\)  
  
-   <xref:System.Drawing.FontFamily.GetLineSpacing%2A>\(FontStyle\)  
  
 Alle von diesen Methoden zurückgegebenen Zahlen entsprechen Schriftentwurfseinheiten; sie sind daher unabhängig von Schriftgrad und Einheiten eines bestimmten <xref:System.Drawing.Font>\-Objekts.  
  
 In der folgenden Abbildung sind die verschiedenen Schriftarteneigenschaften dargestellt.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")  
  
## Beispiel  
 Im folgenden Beispiel werden die Eigenschaften für den Schriftschnitt "Normal" der Schriftfamilie Arial angezeigt.  Durch den Code wird außerdem ein \(auf der Arial\-Kategorie basierendes\) <xref:System.Drawing.Font>\-Objekt mit einem Schriftgrad von 16 Pixel erstellt. Darüber hinaus werden die Eigenschaften für das jeweilige <xref:System.Drawing.Font>\-Objekt \(in Pixel\) angezeigt.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")  
  
 Beachten Sie in der vorangehenden Abbildung die ersten beiden ausgegebenen Zeilen.  Das <xref:System.Drawing.Font>\-Objekt gibt den Schriftgrad 16 und das <xref:System.Drawing.FontFamily>\-Objekt eine Geviertgröße von 2.048 zurück.  Diese beiden Zahlen \(16 und 2.048\) sind der Schlüssel für die Konvertierung von Schriftentwurfseinheiten in Einheiten \(in diesem Fall Pixel\) des <xref:System.Drawing.Font>\-Objekts.  
  
 Beispielsweise können Sie die Oberlänge von Entwurfseinheiten in Pixel wie folgt konvertieren:  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")  
  
 Im folgenden Code wird Text vertikal positioniert, indem der <xref:System.Drawing.PointF.Y%2A>\-Datenmember eines <xref:System.Drawing.PointF>\-Objekts festgelegt wird.  Die y\-Koordinate wird für jede neue Textzeile um `font.Height` erhöht.  Die <xref:System.Drawing.Font.Height%2A>\-Eigenschaft eines <xref:System.Drawing.Font>\-Objekts gibt den Zeilenabstand \(in Pixel\) für das jeweilige <xref:System.Drawing.Font>\-Objekt zurück.  In diesem Beispiel gibt <xref:System.Drawing.Font.Height%2A> die Zahl 19 zurück.  Beachten Sie, dass diese Zahl der Zahl \(zur ganzen Zahl gerundet\) entspricht, die durch Konvertieren der Zeilenabstandseigenschaften in Pixel ermittelt wird.  
  
 Beachten Sie, dass die Geviertgröße nicht die Summe aus Versalhöhe und Unterlänge ist.  Die Summe aus Versalhöhe und Unterlänge wird als Zellenhöhe bezeichnet.  Die Zellenhöhe abzüglich des inneren Zeilenabstands ist gleich der Geviertgröße.  Die Zellenhöhe zuzüglich des äußeren Zeilenabstands ist gleich dem Zeilenvorschub.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)