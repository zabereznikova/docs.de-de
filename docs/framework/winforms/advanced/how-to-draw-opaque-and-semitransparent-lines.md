---
title: "Gewusst wie: Zeichnen deckender und halbtransparenter Linien | Microsoft Docs"
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
  - "Alphablending, Zeichnen von Linien"
  - "Zeichnen, Linien"
  - "Linien, Zeichnen mit Alphablending"
  - "Transparenz, Linien"
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Zeichnen deckender und halbtransparenter Linien
Wenn Sie eine Linie zeichnen, müssen Sie ein <xref:System.Drawing.Pen>\-Objekt an die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse übergeben.  Einer der Parameter des <xref:System.Drawing.Pen.%23ctor%2A>\-Konstruktors ist ein <xref:System.Drawing.Color>\-Objekt.  Um eine nicht transparente Linie zu zeichnen, legen Sie den Alphaanteil der Farbe auf 255 fest.  Um eine halb transparente Linie zu zeichnen, legen Sie den Alphaanteil auf einen beliebigen Wert von 1 bis 254 fest.  
  
 Wenn Sie eine halb transparente Linie vor einem Hintergrund zeichnen, wird Linienfarbe mit den Hintergrundfarben gemischt.  Mit dem Alphaanteil wird das Mischungsverhältnis zwischen Linien\- und Hintergrundfarben angegeben. Bei Alphawerten nahe 0 werden die Hintergrundfarben höher gewichtet, und bei Alphawerten nahe 255 wird die Linienfarbe höher gewichtet.  
  
## Beispiel  
 Im folgenden Beispiel werden erst eine Bitmap und dann drei Linien gezeichnet, die die Bitmap als Hintergrund verwenden.  Für die erste Linie wird ein Alphaanteil von 255 verwendet. Die Linie ist daher nicht transparent.  Die zweite und die dritte Linie verwenden einen Alphaanteil von 128. Sie sind daher halb transparent. Das Hintergrundbild scheint also durch die Linien hindurch.  Die Anweisung, mit der die <xref:System.Drawing.Graphics.CompositingQuality%2A>\-Eigenschaft festgelegt wird, sorgt dafür, dass die Mischung für die dritte Linie unter Verwendung der Gammakorrektur erfolgt.  
  
 In der folgenden Abbildung ist das Ergebnis des angegebenen Codes dargestellt.  
  
 ![Deckend und halb transparent](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)   
 [Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)