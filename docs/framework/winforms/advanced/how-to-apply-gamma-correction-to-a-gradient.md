---
title: "Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf | Microsoft Docs"
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
  - "Farbverlaufspinsel, Gammakorrektur"
  - "Farbverläufe, Gammakorrektur"
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf
Sie können die Gammakorrektur für einen Pinsel mit linearem Farbverlauf aktivieren, indem Sie für seine <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>\-Eigenschaft `true` festlegen.  Sie können die Gammakorrektur deaktivieren, indem Sie für die <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>\-Eigenschaft `false` festlegen.  Die Gammakorrektur ist standardmäßig deaktiviert.  
  
## Beispiel  
 Im Beispiel wird ein Pinsel mit linearem Farbverlauf erstellt und zum Ausfüllen von zwei Rechtecken verwendet.  Das erste Rechteck wird ohne und das zweite Rechteck mit Gammakorrektur ausgefüllt.  
  
 In der folgenden Abbildung sind die beiden ausgefüllten Rechtecke dargestellt.  Das obere Rechteck \(ohne Gammakorrektur\) wirkt in der Mitte dunkler.  Das untere Rechteck \(mit Gammakorrektur\) weist eine gleichmäßige Intensität auf.  
  
 ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>   
 [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)