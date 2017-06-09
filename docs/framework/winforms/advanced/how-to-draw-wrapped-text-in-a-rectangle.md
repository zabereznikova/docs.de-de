---
title: "Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck | Microsoft Docs"
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
  - "Zeichenfolgen [Windows Forms], Zeichnen in einem Rechteck"
  - "Text [Windows Forms], Zeichnen in einem Rechteck"
  - "Windows Forms, Zeichnen von Text in einem Rechteck"
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck
Sie können umbrochenen Text in einem Rechteck zeichnen, in dem Sie die überladene <xref:System.Drawing.Graphics.DrawString%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse verwenden, die einen <xref:System.Drawing.Rectangle>\-Parameter oder <xref:System.Drawing.RectangleF>\-Parameter akzeptiert.  Sie benötigen außerdem einen <xref:System.Drawing.Brush> und einen <xref:System.Drawing.Font>.  
  
 Sie können umbrochenen Text auch in einem Rechteck zeichnen, indem Sie die überladene <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode des <xref:System.Windows.Forms.TextRenderer> verwenden, der einen <xref:System.Drawing.Rectangle>\-Parameter und einen <xref:System.Windows.Forms.TextFormatFlags>\-Parameter akzeptiert.  Sie benötigen außerdem einen <xref:System.Drawing.Color> und einen <xref:System.Drawing.Font>.  
  
 In der folgenden Abbildung wird der anhand der <xref:System.Drawing.Graphics.DrawString%2A>\-Methode im Rechteck gezeichnete Text dargestellt.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### So zeichnen Sie umbrochenen Text in einem Rechteck mit GDI\+  
  
1.  Verwenden Sie die überladene <xref:System.Drawing.Graphics.DrawString%2A>\-Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> und <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### So zeichnen Sie umbrochenen Text in einem Rechteck mit GDI  
  
1.  Verwenden Sie den <xref:System.Windows.Forms.TextFormatFlags>\-Enumerationswert, um den Text anzugeben, der in die überladene <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode eingebunden werden soll, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> und <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## Kompilieren des Codes  
 Für die vorherigen Beispiele ist Folgendes erforderlich:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [Gewusst wie: Zeichnen von Text an einer angegebenen Position](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)