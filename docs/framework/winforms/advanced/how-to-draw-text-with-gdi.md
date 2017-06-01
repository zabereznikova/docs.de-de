---
title: "Gewusst wie: Zeichnen von Text mit GDI | Microsoft Docs"
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
  - "Zeichnen, Text"
  - "GDI, Zeichnen von Text [Windows Forms]"
  - "Text, Zeichnen mit TextRenderer"
  - "Windows Forms, Zeichnen von Text mit GDI"
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zeichnen von Text mit GDI
Über die <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode in der <xref:System.Windows.Forms.TextRenderer>\-Klasse haben Sie Zugriff auf [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\-Funktionen, mit denen Sie Text in einem Formular oder Steuerelement zeichnen können.  Das Rendern von Text in [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bietet normalerweise eine bessere Leistung und genauere Abmessungen für Text als [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methoden der <xref:System.Windows.Forms.TextRenderer>\-Klasse werden für das Drucken nicht unterstützt.  Verwenden Sie beim Drucken immer die <xref:System.Drawing.Graphics.DrawString%2A>\-Methoden der <xref:System.Drawing.Graphics>\-Klasse.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Text mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode über mehrere Zeilen innerhalb eines Rechtecks gezeichnet wird.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Um Text mit der <xref:System.Windows.Forms.TextRenderer>\-Klasse zu rendern, benötigen Sie <xref:System.Drawing.IDeviceContext>, z. B. <xref:System.Drawing.Graphics> und <xref:System.Drawing.Font>, eine Position, an der der Text gezeichnet wird, sowie die Farbe, in der der Text gezeichnet wird.  Optional können Sie die Textformatierung angeben, indem Sie die <xref:System.Windows.Forms.TextFormatFlags>\-Enumeration verwenden.  
  
 Weitere Informationen zum Abrufen von <xref:System.Drawing.Graphics> finden Sie unter [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  Weitere Informationen zum Erstellen von <xref:System.Drawing.Font> finden Sie unter [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## Kompilieren des Codes  
 Das vorangehende Codebeispiel ist für die Verwendung mit Windows Forms vorgesehen und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.TextRenderer>   
 <xref:System.Drawing.Font>   
 <xref:System.Drawing.Color>   
 <xref:System.Drawing.Color>   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)