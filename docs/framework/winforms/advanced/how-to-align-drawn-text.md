---
title: "Gewusst wie: Ausrichten von gezeichnetem Text | Microsoft Docs"
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
  - "Text, Ausrichten"
  - "Windows Forms, Ausrichten von gezeichnetem Text"
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Ausrichten von gezeichnetem Text
Beim benutzerdefinierten Zeichnen ist das Zentrieren von gezeichnetem Text in einem Formular oder Steuerelement häufig erwünscht.  Sie können Text, der mit der <xref:System.Drawing.Graphics.DrawString%2A>\-Methode oder <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode gezeichnet wurde, problemlos ausrichten, indem Sie das richtige Formatierungsobjekt erstellen und die erforderlichen Formatflags festlegen.  
  
### So zeichnen Sie zentrierten Text mit GDI\+ \(DrawString\)  
  
1.  Verwenden Sie <xref:System.Drawing.StringFormat> mit der entsprechenden <xref:System.Drawing.Graphics.DrawString%2A>\-Methode, um zentrierten Text anzugeben.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### So zeichnen Sie zentrierten Text mit GDI \(DrawText\)  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.TextFormatFlags>\-Enumeration zum Umbrechen sowie zum vertikalen oder horizontalen Zentrieren von Text mit der entsprechenden <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## Kompilieren des Codes  
 Die vorangehenden Codebeispiele sind für die Verwendung mit Windows Forms vorgesehen und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)