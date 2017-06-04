---
title: "Gewusst wie: Zeichnen von Text an einer angegebenen Position | Microsoft Docs"
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
  - "Zeichnen von Text"
  - "Zeichnen von Text, Angegebene Positionen [Windows Forms]"
  - "Text, Zeichnen an angegebenen Positionen [Windows Forms]"
  - "Windows Forms, Zeichen von Text an einer angegebenen Position"
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Zeichnen von Text an einer angegebenen Position
Beim benutzerdefinierten Zeichnen können Sie Text in einer einzelnen Zeile zeichnen, die an einem angegebenen Punkt beginnt.  Verwenden Sie hierfür die überladene <xref:System.Drawing.Graphics.DrawString%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse, die einen <xref:System.Drawing.Point>\-Parameter oder <xref:System.Drawing.PointF>\-Parameter akzeptiert.  Für die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode sind zudem ein <xref:System.Drawing.Brush> und ein <xref:System.Drawing.Font> erforderlich.  
  
 Sie können auch die überladene <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode von <xref:System.Windows.Forms.TextRenderer> verwenden, die einen <xref:System.Drawing.Point> akzeptiert.  Für <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sind zudem eine <xref:System.Drawing.Color> und ein <xref:System.Drawing.Font> erforderlich.  
  
 Die folgende Abbildung zeigt die Ausgabe des Textes, der mit der <xref:System.Drawing.Graphics.DrawString%2A>\-Methode an einem angegebenen Punkt gezeichnet wurde.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### So zeichnen Sie eine Textzeile mit GDI\+  
  
1.  Verwenden Sie die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF>, <xref:System.Drawing.Font> und <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### So zeichnen Sie eine Textzeile mit GDI\+  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.TextRenderer.DrawText%2A>\-Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Point>, <xref:System.Drawing.Font> und <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## Kompilieren des Codes  
 Für die vorherigen Beispiele ist Folgendes erforderlich:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)