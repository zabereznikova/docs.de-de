---
title: "Gewusst wie: Zeichnen von Text in einem Windows&#160;Form | Microsoft Docs"
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
  - "Formulare, Zeichnen von Text"
  - "Text, Zeichnen"
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Zeichnen von Text in einem Windows&#160;Form
Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode von <xref:System.Drawing.Graphics> verwendet wird, um Text auf einem Formular zu zeichnen.  Wahlweise können Sie hierfür <xref:System.Windows.Forms.TextRenderer> verwenden.  Weitere Informationen finden Sie unter [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## Kompilieren des Codes  
 Sie können die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode nicht im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler aufrufen.  Der gezeichnete Inhalt wird nicht neu gezeichnet, wenn die Größe des Formulars geändert oder das Formular durch ein anderes Formular verdeckt wird.  Wenn der Inhalt automatisch neu gezeichnet werden soll, müssen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschreiben.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Die Schriftart Arial ist nicht installiert.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.TextFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)