---
title: "Gewusst wie: Verknüpfen von Linien"
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
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d12cc7b4b4c878ec812190fd56a1face64118ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-join-lines"></a>Gewusst wie: Verknüpfen von Linien
Ein Join Zeile ist der allgemeinen Bereich, der zwei Zeilen gebildet wird, deren Enden erfüllen oder sich überlappen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]bietet drei Linienarten Join: Linienverbindungsstile, abschrägungen und gerundet wird. Linienverbindungsstil ist eine Eigenschaft der <xref:System.Drawing.Pen> Klasse. Wenn Sie einen Linienverbindungsstil für eine <xref:System.Drawing.Pen> -Objekt, dass auf alle miteinander verbundenen Linien in einem Linienverbindungsstil angewendet werden <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt mit diesem Stift gezeichnet.  
  
 Die folgende Abbildung zeigt die Ergebnisse des Beispiels Join abgeschrägte Zeile.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>Beispiel  
 Sie können die Linienverbindungsstil angeben, mit der <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft von der <xref:System.Drawing.Pen> Klasse. Das Beispiel zeigt einen Join abgeschrägte Zeile zwischen einer horizontalen Linie und eine vertikale Linie. Im folgenden Code wird der Wert <xref:System.Drawing.Drawing2D.LineJoin.Bevel> zugewiesene der <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft ist ein Mitglied der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration. Die anderen Member der der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration sind <xref:System.Drawing.Drawing2D.LineJoin.Miter> und <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
