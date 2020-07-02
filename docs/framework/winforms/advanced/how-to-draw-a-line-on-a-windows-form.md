---
title: 'Vorgehensweise: Zeichnen einer Linie in Windows Forms'
description: Erfahren Sie, wie Sie eine Linie in einem Formular zeichnen, indem Sie das Paint-Ereignis behandeln, und führen Sie dann die Zeichnung mithilfe der Graphics-Eigenschaft von "pinteventargs" aus.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621625"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Vorgehensweise: Zeichnen einer Linie in Windows Forms
In diesem Beispiel wird eine Zeile in einem Formular gezeichnet. Wenn Sie in einem Formular zeichnen, behandeln Sie in der Regel das- <xref:System.Windows.Forms.Control.Paint> Ereignis des Formulars und führen die Zeichnung mithilfe der- <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft von aus <xref:System.Windows.Forms.PaintEventArgs> , wie in diesem Beispiel gezeigt.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Sie sollten immer <xref:System.IDisposable.Dispose%2A> für alle-Objekte, die Systemressourcen verwenden, wie z. b.-Objekte, Abrufen <xref:System.Drawing.Pen> .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
