---
title: 'Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 96e8f5babb194cfd2934c2bb71f3007483c68fd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520837"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms
Dieses Beispiel zeichnet ein ausgefülltes Rechteck in einem Formular an.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler. Der gezeichnete Inhalt wird nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt. Damit der Inhalt automatisch neu gezeichnet werden soll, sollten Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics> Objekte.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics.FillRectangle%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Pinsel und gefüllte Formen in GDI+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
