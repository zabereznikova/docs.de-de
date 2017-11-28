---
title: 'Gewusst wie: Festlegen von Stiftbreite und -ausrichtung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ed2a28c49554c686abb5e2635ab35b746b83465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a>Gewusst wie: Festlegen von Stiftbreite und -ausrichtung
Beim Erstellen einer <xref:System.Drawing.Pen>, Sie können die Stiftbreite als eines der Argumente an den Konstruktor bereitstellen. Sie können auch die Stiftbreite mit ändern die <xref:System.Drawing.Pen.Width%2A> Eigenschaft von der <xref:System.Drawing.Pen> Klasse.  
  
 Eine theoretische Linie hat eine Breite von 0. Wenn Sie eine Linie, die 1 Pixel breit ist zeichnen, werden die Pixel auf der theoretischen Linie zentriert. Wenn Sie eine Linie, die mehr als ein Pixel breit ist zeichnen, sind entweder auf der theoretischen Linie zentriert die Pixel oder auf einer Seite eines theoretischen Linie angezeigt wird. Festlegen der Stift Alignment-Eigenschaft des eine <xref:System.Drawing.Pen> um zu bestimmen, wie die mit diesem Stift gezeichneten Pixel relativ zum theoretischen Linien positioniert werden.  
  
 Die Werte <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, und <xref:System.Drawing.Drawing2D.PenAlignment.Inset> , die angezeigt werden, in der folgenden Codebeispiele sind Mitglied der <xref:System.Drawing.Drawing2D.PenAlignment> Enumeration.  
  
 Im folgenden Codebeispiel wird eine Linie zweimal gezeichnet: einmal mit einem schwarzen Stift der Breite 1 und einmal mit einem grünen Stift der Breite 10.  
  
### <a name="to-vary-the-width-of-a-pen"></a>Um die Breite eines Stiftes zu variieren.  
  
-   Legen Sie den Wert von der <xref:System.Drawing.Pen.Alignment%2A> Eigenschaft <xref:System.Drawing.Drawing2D.PenAlignment.Center> (Standardeinstellung) angeben, dass mit dem grünen Stift gezeichneten Pixel auf der theoretischen Linie zentriert werden soll. Die folgende Abbildung zeigt die resultierenden Zeile.  
  
     ![Stifte](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")  
  
     Im folgenden Codebeispiel wird ein Rechteck zweimal gezeichnet: einmal mit einem schwarzen Stift der Breite 1 und einmal mit einem grünen Stift der Breite 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>So ändern Sie die Ausrichtung eines Stiftes  
  
-   Legen Sie den Wert von der <xref:System.Drawing.Pen.Alignment%2A> Eigenschaft <xref:System.Drawing.Drawing2D.PenAlignment.Center> um anzugeben, dass die mit dem grünen Stift gezeichneten Pixel auf die Begrenzung des Rechtecks zentriert werden soll.  
  
     Die folgende Abbildung zeigt das resultierende Rechteck.  
  
     ![Stifte](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>So erstellen ein Stift inset  
  
-   Ändern Sie den grünen Stift Ausrichtung, indem die dritte Anweisung im vorangehenden Codebeispiel wird wie folgt ändern:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Nun die Pixel in der breiten grünen Zeile innerhalb des Rechtecks angezeigt, wie in der folgenden Abbildung dargestellt.  
  
     ![Stifte](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
