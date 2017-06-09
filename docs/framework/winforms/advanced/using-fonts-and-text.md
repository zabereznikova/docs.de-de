---
title: "Verwenden von Schriftarten und Text | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Schriftarten und Text"
  - "Schriftarten, Verwenden in Windows Forms"
  - "GDI, Zeichnen von Text [Windows Forms]"
  - "Zeichenfolgen [Windows Forms], Zeichnen in Windows Forms"
  - "Text [Windows Forms], Zeichnen in Windows Forms"
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Verwenden von Schriftarten und Text
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bieten mehrere Klassen zum Zeichnen von Text in Windows Forms.  Die <xref:System.Drawing.Graphics>\-Klasse in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] verfügt über mehrere <xref:System.Drawing.Graphics.DrawString%2A>\-Methoden, mit denen Sie verschiedene Textfunktionen festlegen können, z. B. Position, umschließendes Rechteck, Schriftart und Format.  Zusätzlich können Sie Text in [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mithilfe der statischen <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode und der <xref:System.Windows.Forms.TextRenderer.MeasureText%2A>\-Methode, die von der `TextRenderer`\-Klasse bereitgestellt wird, zeichnen und messen.  Über die [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\-Methoden können Sie außerdem Speicherort, Schriftart und Format angeben.  Zum Rendern von Text können Sie entweder [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oder [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] auswählen. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bietet im Allgemeinen jedoch bessere Leistung und genauere Textabmessungen.  Andere Klassen, die für das Rendern von Text verwendet werden können, sind `FontFamily`, `Font`, <xref:System.Drawing.StringFormat> und `TextFormatFlags`.  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Erläutert das Erstellen des `Font`\-Objekts und des `FontFamily`\-Objekts.  
  
 [Gewusst wie: Zeichnen von Text an einer angegebenen Position](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Erläutert das Platzieren von Text an einer bestimmten Position mithilfe von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Erläutert das Platzieren von Text in einem Rechteck mithilfe von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Veranschaulicht, wie [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text verwendet wird.  
  
 [Gewusst wie: Ausrichten von gezeichnetem Text](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Veranschaulicht das Formatieren von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\- und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\-Text.  
  
 [Gewusst wie: Erstellen von vertikalem Text](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Beschreibt das Zeichnen von vertikal ausgerichtetem Text mithilfe von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Veranschaulicht das Zeichnen von Text mit Tabstopps mithilfe von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Gewusst wie: Auflisten installierter Schriftarten](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Erläutert das Auflisten der Namen installierter Schriftarten.  
  
 [Gewusst wie: Erstellen einer privaten Schriftartenauflistung](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Beschreibt das Erstellen eines <xref:System.Drawing.Text.PrivateFontCollection>\-Objekts.  
  
 [Gewusst wie: Abrufen von Schriftarteigenschaften](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Veranschaulicht das Abrufen von Schriftarteigenschaften wie Versalhöhe und Unterlänge.  
  
 [Gewusst wie: Verwenden der Bildkantenglättung mit Text](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 Erläutert, wie das Antialiasing beim Zeichnen von Text verwendet wird.  
  
## Referenz  
 <xref:System.Drawing.Font>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Drawing.FontFamily>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.