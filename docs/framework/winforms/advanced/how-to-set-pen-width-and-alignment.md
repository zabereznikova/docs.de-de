---
title: "Gewusst wie: Festlegen von Stiftbreite und -ausrichtung | Microsoft Docs"
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
  - "Stifte, Festlegen der Ausrichtung"
  - "Stifte, Festlegen der Breite"
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Festlegen von Stiftbreite und -ausrichtung
Wenn Sie ein <xref:System.Drawing.Pen>\-Objekt erstellen, können Sie die Stiftbreite zusammen mit anderen Argumenten an den Konstruktor übergeben.  Darüber hinaus können Sie die Stiftbreite mit der <xref:System.Drawing.Pen.Width%2A>\-Eigenschaft der <xref:System.Drawing.Pen>\-Klasse ändern.  
  
 Eine theoretische Linie hat die Breite 0.  Wenn Sie eine Linie mit einer Breite von einem Pixel zeichnen, werden die Pixel auf der theoretischen Linie zentriert.  Wenn Sie eine Linie mit einer Breite von mehr als 1 Pixel zeichnen, werden die Pixel entweder auf der theoretischen Linie zentriert, oder sie werden auf einer Seite der theoretischen Linie angezeigt.  Indem Sie für ein <xref:System.Drawing.Pen>\-Objekt die Stiftausrichtungseigenschaft festlegen, können Sie bestimmen, wie die mit diesem Stift gezeichneten Pixel relativ zu theoretischen Linien positioniert werden.  
  
 Die Werte <xref:System.Drawing.Drawing2D.PenAlignment>, <xref:System.Drawing.Drawing2D.PenAlignment> und <xref:System.Drawing.Drawing2D.PenAlignment> in den folgenden Codebeispielen sind Member der <xref:System.Drawing.Drawing2D.PenAlignment>\-Enumeration.  
  
 Im folgenden Codebeispiel wird eine Linie zweimal gezeichnet: einmal mit einem schwarzen Stift der Breite 1 und ein anderes Mal mit einem grünen Stift der Breite 10.  
  
### So variieren Sie die Stiftbreite  
  
-   Geben Sie für die <xref:System.Drawing.Pen.Alignment%2A>\-Eigenschaft den Wert <xref:System.Drawing.Drawing2D.PenAlignment> \(Standard\) an, um festzulegen, dass die mit dem grünen Stift gezeichneten Pixel auf der theoretischen Linie zentriert werden.  In der folgenden Abbildung ist die resultierende Linie dargestellt.  
  
     ![Stifte](../../../../docs/framework/winforms/advanced/media/pens1a.png "pens1A")  
  
     Im folgenden Codebeispiel wird ein Rechteck zweimal gezeichnet: einmal mit einem schwarzen Stift der Breite 1 und ein anderes Mal mit einem grünen Stift der Breite 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### So ändern Sie die Stiftausrichtung  
  
-   Geben Sie für die <xref:System.Drawing.Pen.Alignment%2A>\-Eigenschaft den Wert <xref:System.Drawing.Drawing2D.PenAlignment> an, um festzulegen, dass die mit dem grünen Stift gezeichneten Pixel auf der Begrenzung des Rechtecks zentriert werden.  
  
     In der folgenden Abbildung ist das Rechteck dargestellt, das sich daraus ergibt.  
  
     ![Stifte](../../../../docs/framework/winforms/advanced/media/pens2.png "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### So erstellen Sie einen abgesenkten Stift  
  
-   Ändern Sie die Ausrichtung des grünen Stiftes, indem Sie die dritte Anweisung im vorangehenden Codebeispiel wie folgt ändern:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Die Pixel in der breiten grünen Linie werden nun auf der Innenseite des Rechtecks angezeigt, wie in der folgenden Abbildung dargestellt.  
  
     ![Stifte](../../../../docs/framework/winforms/advanced/media/pens3.png "pens3")  
  
## Siehe auch  
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)