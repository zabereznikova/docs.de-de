---
title: 'Vorgehensweise: Zeichnen eines ausgefüllten Rechtecks in Windows Forms'
description: Erfahren Sie, wie Sie ein ausgefülltes Rechteck Programm gesteuert in einem Windows Form zeichnen. Erfahren Sie auch mehr über das Kompilieren von Code.
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
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621638"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Vorgehensweise: Zeichnen eines ausgefüllten Rechtecks in Windows Forms
In diesem Beispiel wird ein ausgefülltes Rechteck in einem Formular gezeichnet.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Methode kann nicht im- <xref:System.Windows.Forms.Form.Load> Ereignishandler aufgerufen werden. Der gezeichnete Inhalt wird nicht neu gezeichnet, wenn die Größe des Formulars geändert oder durch ein anderes Formular verdeckt wird. Damit Ihre Inhalte automatisch neu gezeichnet werden, sollten Sie die- <xref:System.Windows.Forms.Control.OnPaint%2A> Methode überschreiben.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Sie sollten immer <xref:System.IDisposable.Dispose%2A> für alle-Objekte, die Systemressourcen nutzen, z <xref:System.Drawing.Brush> . b.-und-Objekte, Abrufen <xref:System.Drawing.Graphics> .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
- [Pinsel und gefüllte Formen in GDI+](brushes-and-filled-shapes-in-gdi.md)
