---
title: 'Vorgehensweise: Verwenden eines Stiftes zum Zeichnen von Linien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: e24d02c2c6ab7537f968c013eb91838eb0bb812a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730931"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Vorgehensweise: Verwenden eines Stiftes zum Zeichnen von Linien
Um Linien zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawLine%2A> -Methode, und die <xref:System.Drawing.Pen> Objektspeicher Features der Zeile, z. B. Farbe und Breite.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeichnet eine Linie von (20, 10), (300, 100). Die erste Anweisung verwendet die <xref:System.Drawing.Pen.%23ctor%2A> Klassenkonstruktor einen schwarzen Stift erstellen. Das einzige Argument übergeben wird, um die <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor ist eine <xref:System.Drawing.Color> Objekt erstellt wurde, mit der <xref:System.Drawing.Color.FromArgb%2A> Methode. Die Werte, die zum Erstellen der <xref:System.Drawing.Color> Objekt – (255, 0, 0, 0) – entsprechen, die alpha, roten, grünen und blauen-Komponenten der Farbe. Diese Werte definieren, einen nicht transparenten schwarzen Stift.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Pen>
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Stifte, Linien und Rechtecke in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
