---
title: "Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten | Microsoft Docs"
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
  - "Schriftartfamilien, Erstellen"
  - "Schriftarten, Erstellen"
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten
In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] werden Schriftarten, die dasselbe Schriftbild, aber unterschiedliche Schriftschnitte haben, in Schriftfamilien zusammengefasst.  Die Schriftfamilie "Arial" enthält beispielsweise die folgenden Schriftarten:  
  
-   Arial Normal  
  
-   Arial Fett  
  
-   Arial Kursiv  
  
-   Arial Fett Kursiv  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] setzt diese Familien aus vier Schriftschnitten zusammen: Normal, Fett, Kursiv und Fett kursiv.  Adjektive wie *Narrow* und *Rounded* werden nicht als Schriftschnitte bezeichnet, sondern sind vielmehr Bestandteil des Familiennamens.  Arial Narrow ist beispielsweise eine Schriftfamilie mit folgendem Inhalt:  
  
-   Arial Narrow Normal  
  
-   Arial Narrow Fett  
  
-   Arial Narrow Kursiv  
  
-   Arial Narrow Fett Kursiv  
  
 Bevor Sie mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Text zeichnen können, müssen Sie ein <xref:System.Drawing.FontFamily>\-Objekt und ein <xref:System.Drawing.Font>\-Objekt erstellen.  Durch das <xref:System.Drawing.FontFamily>\-Objekt wird die Schriftart \(z. B. Arial\) festgelegt, während das <xref:System.Drawing.Font>\-Objekt Schriftgrad, Schriftschnitt und Einheiten bestimmt.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Arial\-Schriftart mit dem Schriftschnitt "Normal" und einem Schriftgrad von 16 Pixel erstellt.  Im folgenden Code ist das erste an den <xref:System.Drawing.Font.%23ctor%2A>\-Konstruktor übergebene Argument das <xref:System.Drawing.FontFamily>\-Objekt.  Durch das zweite Argument wird der Schriftgrad der Schriftart festgelegt; dieser wird in Einheiten gemessen, die durch das vierte Argument vorgegeben werden.  Durch das dritte Argument wird der Schriftschnitt identifiziert.  
  
 <xref:System.Drawing.GraphicsUnit> ist ein Member der <xref:System.Drawing.GraphicsUnit>\-Enumeration, und <xref:System.Drawing.FontStyle> ist ein Member der <xref:System.Drawing.FontStyle>\-Enumeration.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)