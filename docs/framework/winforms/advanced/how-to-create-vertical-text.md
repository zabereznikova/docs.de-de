---
title: "Gewusst wie: Erstellen von vertikalem Text | Microsoft Docs"
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
  - "Zeichenfolgen [Windows Forms], Zeichnen von vertikalen"
  - "Text [Windows Forms], Zeichnen von vertikalen"
  - "Vertikaler Text, Zeichnen"
  - "Windows Forms, Zeichnen von vertikalem Text"
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen von vertikalem Text
Über ein <xref:System.Drawing.StringFormat>\-Objekt können Sie festlegen, ob Text vertikal oder horizontal gezeichnet wird.  
  
## Beispiel  
 Im folgenden Beispiel wird der Wert <xref:System.Drawing.StringFormatFlags> der <xref:System.Drawing.StringFormat.FormatFlags%2A>\-Eigenschaft eines <xref:System.Drawing.StringFormat>\-Objekts zugewiesen.  Dieses <xref:System.Drawing.StringFormat>\-Objekt wird an die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse übergeben.  Der Wert <xref:System.Drawing.StringFormatFlags> ist ein Member der <xref:System.Drawing.StringFormatFlags>\-Enumeration.  
  
 In der folgenden Abbildung ist der vertikale Text dargestellt.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## Kompilieren des Codes  
  
-   Das vorangehende Beispiel ist für die Verwendung mit Windows Forms vorgesehen und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e` , einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)