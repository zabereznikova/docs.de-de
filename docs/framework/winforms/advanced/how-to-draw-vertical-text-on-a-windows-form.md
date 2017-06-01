---
title: "Gewusst wie: Zeichnen von vertikalem Text in einem Windows&#160;Form | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StringFormat.FormatFlags"
  - "Graphics.DrawString"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zeichenfolgen [Windows Forms], Zeichnen von vertikalen"
  - "Text [Windows Forms], Zeichnen"
  - "Text [Windows Forms], Zeichnen von vertikalen"
  - "Text [Windows Forms], Vertikaler Text"
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zeichnen von vertikalem Text in einem Windows&#160;Form
Im folgenden Codebeispiel wird gezeigt, wie vertikaler Text mithilfe der <xref:System.Drawing.Graphics.DrawString%2A>\-Methode von <xref:System.Drawing.Graphics> auf einem Formular gezeichnet wird.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## Kompilieren des Codes  
 Sie können diese Methode nicht im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler aufrufen.  Der gezeichnete Inhalt wird nicht neu gezeichnet, wenn die Größe des Formulars geändert oder das Formular durch ein anderes Formular verdeckt wird.  Wenn der Inhalt automatisch neu gezeichnet werden soll, müssen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschreiben.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Die Schriftart Arial ist nicht installiert.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)