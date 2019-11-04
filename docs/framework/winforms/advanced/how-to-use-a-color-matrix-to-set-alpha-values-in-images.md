---
title: 'Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423735"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern
Die <xref:System.Drawing.Bitmap>-Klasse (die von der <xref:System.Drawing.Image>-Klasse erbt) und die <xref:System.Drawing.Imaging.ImageAttributes>-Klasse bieten Funktionen zum erhalten und Festlegen von Pixelwerten. Sie können die <xref:System.Drawing.Imaging.ImageAttributes>-Klasse verwenden, um die Alpha Werte für ein gesamtes Bild zu ändern, oder Sie können die <xref:System.Drawing.Bitmap.SetPixel%2A>-Methode der <xref:System.Drawing.Bitmap>-Klasse zum Ändern einzelner Pixelwerte verwenden.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Drawing.Imaging.ImageAttributes>-Klasse verfügt über zahlreiche Eigenschaften, mit denen Sie Bilder während des Renderings ändern können. Im folgenden Beispiel wird ein <xref:System.Drawing.Imaging.ImageAttributes>-Objekt verwendet, um alle Alpha Werte auf 80 Prozent ihrer Werte festzulegen. Dies erfolgt durch Initialisieren einer Farbmatrix und Festlegen des alphaskalierungswerts in der Matrix auf 0,8. Die Adresse der Farbmatrix wird an die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A>-Methode des <xref:System.Drawing.Imaging.ImageAttributes>-Objekts und das <xref:System.Drawing.Imaging.ImageAttributes>-Objekt an die <xref:System.Drawing.Graphics.DrawString%2A>-Methode des <xref:System.Drawing.Graphics> Objekts übermittelt.  
  
 Während des Renderings werden die Alpha Werte in der Bitmap in 80 Prozent ihrer Art konvertiert. Dies führt zu einem Bild, das mit dem Hintergrund kombiniert wird. Wie die folgende Abbildung zeigt, sieht das Bitmap-Bild transparent aus. Sie sehen, dass die schwarze Linie durchlaufen wird.  
  
 ![Screenshot der Alpha Mischung mithilfe einer Matrix](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")  
  
 Wenn sich das Bild über dem weißen Teil des Hintergrunds befindet, wurde das Bild mit der Farbe weiß gemischt. Wenn das Bild die schwarze Linie überschreitet, wird das Bild mit der Farbe schwarz gemischt.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, bei dem es sich um einen Parameter <xref:System.Windows.Forms.PaintEventHandler>handelt.  
  
## <a name="see-also"></a>Siehe auch

- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Alphablending von Linien und Füllungen](alpha-blending-lines-and-fills.md)
