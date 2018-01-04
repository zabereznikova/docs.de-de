---
title: 'Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Rechtecken'
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
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7257fa21432ec5d849a257f4a5e412515f474363
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Rechtecken
Zum Zeichnen von Rechtecken, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawRectangle%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert die Funktionen der Zeile, z. B. Farbe und Breite.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet ein Rechteck mit der linken oberen Ecke an (10, 10). Das Rechteck hat eine Breite von 100 und eine Höhe von 50. Das zweite Argument zu übergeben, um die <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor gibt an, dass die Stiftbreite 5 Pixel beträgt.  
  
 Wenn das Rechteck gezeichnet wird, ist der Stift auf der Begrenzung des Rechtecks zentriert. Da die Stiftbreite 5 ist, werden die Seiten des Rechtecks 5 Pixel breit, z. B. 1 Pixel gezeichnet wird auf die Begrenzung selbst, 2 Pixel innerhalb gezeichnet werden, und 2 Pixel an der Außenseite gezeichnet werden. Ausführliche Informationen auf Stift Ausrichtung finden Sie unter [Vorgehensweise: Festlegen von Stiftbreite und-Ausrichtung](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).  
  
 Die folgende Abbildung zeigt das resultierende Rechteck. Die gepunkteten Linien anzeigen, in denen das Rechteck gezeichnet worden wäre, wenn die Stiftbreite ein Pixel gewesen wäre. Die vergrößerte Ansicht von der linken oberen Ecke des Rechtecks zeigt, dass die dicken schwarzen Linien auf die gepunktete Linien zentriert werden.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
