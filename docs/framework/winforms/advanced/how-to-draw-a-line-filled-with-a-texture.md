---
title: 'Gewusst wie: Zeichnen einer mit einer Textur ausgefüllten Linie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 1895c752340d8d764205b5a32b9af0861303841a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Gewusst wie: Zeichnen einer mit einer Textur ausgefüllten Linie
Statt eine Linie mit einer Volltonfarbe, können Sie eine Zeile mit einer Textur zeichnen. Zum Zeichnen von Linien und Kurven mit einer Textur erstellen Sie eine <xref:System.Drawing.TextureBrush> Objekts, und übergeben, die <xref:System.Drawing.TextureBrush> -Objekt an eine <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor. Wenn der Stift eine Linie oder Kurve zeichnet, überdeckt die Strichbreite des Stifts bestimmte Pixel gekachelt, und die Bitmap der Texturpinsel zugeordneten wird verwendet, um die Ebene (unsichtbar) Kachel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Bitmap> Objekt aus der Datei `Texture1.jpg`. Dieser Bitmap dient zum Erstellen einer <xref:System.Drawing.TextureBrush> -Objekt, und die <xref:System.Drawing.TextureBrush> Objekt dient zum Erstellen einer <xref:System.Drawing.Pen> Objekt. Der Aufruf von <xref:System.Drawing.Graphics.DrawImage%2A> zeichnet die Bitmap mit der linken oberen Ecke an (0, 0). Der Aufruf von <xref:System.Drawing.Graphics.DrawEllipse%2A> verwendet die <xref:System.Drawing.Pen> Objekt zum Zeichnen einer texturierten Ellipse.  
  
 Die folgende Abbildung zeigt die Bitmap und der texturierten Ellipse.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Windows Form, und behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis. Fügen Sie den vorangehenden Code in der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Ersetzen Sie `Texture.jpg` mit einem Bild auf Ihrem System ungültig.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
