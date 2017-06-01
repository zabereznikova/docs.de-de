---
title: "Gewusst wie: Zeichnen einer mit einer Textur ausgef&#252;llten Linie | Microsoft Docs"
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
  - "Zeichnen von Linien, Struktur"
  - "Zeichnen, Linien"
  - "Linien, Struktur"
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Zeichnen einer mit einer Textur ausgef&#252;llten Linie
Anstatt mit einer Volltonfarbe können Sie eine Linie auch mit einer Textur zeichnen.  Um Linien und Kurven mit einer Textur zu zeichnen, erstellen Sie ein <xref:System.Drawing.TextureBrush>\-Objekt und übergeben dieses <xref:System.Drawing.TextureBrush>\-Objekt an einen <xref:System.Drawing.Pen.%23ctor%2A>\-Konstruktor.  Durch die mit dem Texturpinsel verknüpfte Bitmap wird die Ebene \(unsichtbar\) gekachelt. Wenn Sie dann mit dem Stift eine Linie oder Kurve zeichnen, werden durch die Strichführung bestimmte Pixel der gekachelten Textur "aufgedeckt".  
  
## Beispiel  
 Im folgenden Beispiel wird aus der Datei  `Texture1.jpg` ein <xref:System.Drawing.Bitmap>\-Objekt erstellt.  Diese Bitmap wird zum Erstellen eines <xref:System.Drawing.TextureBrush>\-Objekts und das <xref:System.Drawing.TextureBrush>\-Objekt zum Erstellen eines <xref:System.Drawing.Pen>\-Objekts verwendet.  Durch Aufrufen von <xref:System.Drawing.Graphics.DrawImage%2A> wird die Bitmap mit der oberen linken Ecke an der Position \(0, 0\) gezeichnet.  Der Aufruf von <xref:System.Drawing.Graphics.DrawEllipse%2A> verwendet das <xref:System.Drawing.Pen>\-Objekt zum Zeichnen einer texturierten Ellipse.  
  
 In der folgenden Abbildung sind die Bitmap und die texturierte Ellipse dargestellt.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## Kompilieren des Codes  
 Erstellen Sie ein Windows Form, und verarbeiten Sie das <xref:System.Windows.Forms.Control.Paint>\-Ereignis des Formulars.  Fügen Sie den vorangehenden Code in den <xref:System.Windows.Forms.Control.Paint>\-Ereignishandler ein.  Ersetzen Sie  `Texture.jpg` durch ein für das System gültiges Bild.  
  
## Siehe auch  
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)