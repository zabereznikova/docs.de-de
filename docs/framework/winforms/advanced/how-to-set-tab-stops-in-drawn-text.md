---
title: "Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text | Microsoft Docs"
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
  - "Registerkarten, Gezeichneter Text"
  - "Text, Zeichnen mit Tabstopps"
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text
Sie können Tabstopps für Text festlegen, indem Sie die <xref:System.Drawing.StringFormat.SetTabStops%2A>\-Methode eines <xref:System.Drawing.StringFormat>\-Objekts aufrufen und das <xref:System.Drawing.StringFormat>\-Objekt anschließend an die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse übergeben.  
  
> [!NOTE]
>  Der <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName> unterstützt nicht das Hinzufügen von Tabstopps zu gezeichnetem Text, obwohl Sie vorhandene Tabstopps mit dem <xref:System.Windows.Forms.TextFormatFlags?displayProperty=fullName>\-Flag erweitern können.  
  
## Beispiel  
 Im folgenden Beispiel wurden Tabstopps an den Positionen 150, 250 und 350 gesetzt.  Durch den Code wird anschließend eine tabstoppgetrennte Liste mit Namen und Testergebnissen ausgegeben.  
  
 In der folgenden Abbildung ist der tabstoppgetrennte Text dargestellt.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Im folgenden Code werden zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A>\-Methode übergeben.  Das zweite Argument ist ein Array, das Tabulatoroffsets enthält.  Das erste an <xref:System.Drawing.StringFormat.SetTabStops%2A> übergebene Argument lautet 0. Dies bedeutet, dass der erste Offset im Array von Position 0, also der linken Ecke des umschließenden Rechtecks, gemessen wird.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## Kompilieren des Codes  
  
-   Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)