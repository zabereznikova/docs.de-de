---
title: "Gewusst wie: Zeichnen einer Linie in Windows Forms"
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
f1_keywords: Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 984cdaca14c354ca78118412911c69c282ddd1bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Gewusst wie: Zeichnen einer Linie in Windows Forms
Dieses Beispiel zeichnet eine verbindende Linie in einem Formular. In der Regel, wenn Sie in einem Formular zeichnen, behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis und die Ausführung der Zeichnung mit der <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft von der <xref:System.Windows.Forms.PaintEventArgs>, wie im folgenden Beispiel gezeigt  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Pen> Objekte.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics.DrawLine%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
