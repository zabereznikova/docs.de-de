---
title: 'Vorgehensweise: Zeichnen einer Linie mit Linienenden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: c4a78569f6c0b14c32154611412d6b3ccd8a84ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146210"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Vorgehensweise: Zeichnen einer Linie mit Linienenden
Sie können den Anfang oder Ende einer Zeile in einer von mehreren Formen namens Linienenden zeichnen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] unterstützt verschiedene Linienenden, z. B. Roundrobin, Quadrat, Raute und Pfeilspitze.  
  
## <a name="example"></a>Beispiel  
 Sie können die Linienenden für den Anfang einer Linie (, StartCap), die das Ende einer Zeile (EndCap) oder die Striche eine gestrichelte Linie (DashCap) angeben.  
  
 Im folgende Beispiel zeichnet eine Linie mit einer Pfeilspitze an einem Ende und einem runden Ende am anderen Ende. Die Abbildung zeigt die resultierenden Zeile:  
  
 ![Abbildung der eine Zeile mit einem runden Ende.](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Erstellen Sie ein Windows Form und behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis. Fügen Sie den Beispielcode in die <xref:System.Windows.Forms.Control.Paint> -Ereignishandler übergeben `e` als <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
