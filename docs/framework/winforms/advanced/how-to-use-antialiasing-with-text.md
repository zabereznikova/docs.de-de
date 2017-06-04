---
title: "Gewusst wie: Verwenden der Bildkantengl&#228;ttung mit Text | Microsoft Docs"
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
  - "Antialiasing, Verwenden mit Text"
  - "Zeichenfolgen [Windows Forms], Antialising beim Zeichnen"
  - "Zeichenfolgen [Windows Forms], Glättung von gezeichneten"
  - "Text [Windows Forms], Antialiasing"
  - "Text [Windows Forms], Glättung"
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Verwenden der Bildkantengl&#228;ttung mit Text
Unter *Bildkantenglättung* versteht man das Glätten von gezackten Kanten von gezeichneten Grafiken und Text, um die Darstellung oder Lesbarkeit zu verbessern.  Mit den verwalteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Klassen können Sie geglätteten Text von hoher Qualität sowie Text von geringer Qualität rendern.  In der Regel erfordert das Rendern von qualitativ hochwertigem Text mehr Verarbeitungszeit als das Rendern von Text mit einer geringeren Qualität.  Um die Qualität des Textes zu definieren, legen Sie die <xref:System.Drawing.Graphics.TextRenderingHint%2A>\-Eigenschaft einer <xref:System.Drawing.Graphics> auf ein Element der <xref:System.Drawing.Text.TextRenderingHint>\-Enumeration fest.  
  
## Beispiel  
 Im folgenden Codebeispiel wird Text mit zwei verschiedenen Qualitätseinstellungen gezeichnet.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## Kompilieren des Codes  
 Das vorangehende Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)