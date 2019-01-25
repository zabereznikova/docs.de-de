---
title: 'Vorgehensweise: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern'
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
ms.openlocfilehash: 0e62bee55938e79d1555c463ac770f7b35be20f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578802"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Vorgehensweise: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern
Die <xref:System.Drawing.Bitmap> Klasse (erbt von der <xref:System.Drawing.Image> Klasse) und die <xref:System.Drawing.Imaging.ImageAttributes> -Klasse bieten Funktionen zum Abrufen und Pixelwerte festlegen. Können Sie die <xref:System.Drawing.Imaging.ImageAttributes> Klasse so ändern Sie den Alpha-Werte für ein vollständiges Bild, oder Sie rufen die <xref:System.Drawing.Bitmap.SetPixel%2A> Methode der <xref:System.Drawing.Bitmap> Klasse, um die Pixelwerte der einzelnen ändern.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Drawing.Imaging.ImageAttributes> -Klasse verfügt über viele Eigenschaften, die Sie verwenden können, während des Renderings Bilder ändern. Im folgenden Beispiel eine <xref:System.Drawing.Imaging.ImageAttributes> Objekt wird zum Festlegen der Alphawerte bis 80 Prozent des Originalwerts verwendet. Dies erfolgt durch Initialisieren einer Farbmatrix und den Wert in der Matrix mit 0,8 Skalierung Alpha festlegen. Die Adresse der Farbmatrix wird zum Übergeben der <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> -Methode der der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt, und die <xref:System.Drawing.Imaging.ImageAttributes> -Objekt übergeben wird die <xref:System.Drawing.Graphics.DrawString%2A> -Methode der der <xref:System.Drawing.Graphics> Objekt.  
  
 Während des Renderns, werden die Alpha-Werte in der Bitmap in 80 Prozent der einstellungsänderungen konvertiert. Dies führt zu einem Bild, das mit dem Hintergrund gemischt wird. Wie in die folgende Abbildung gezeigt, sieht das Bitmap-Bild transparent; Sie sehen, dass die durchgehende schwarze Linie durchzogen ist.  
  
 ![Alphablending mit einer Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 Wenn das Bild über im weißen Teil der Hintergrund ist, hat das Image mit die Farbe Weiß gemischt wurden. In dem das Bild für die schwarze Linie schneidet, wird das Image mit die Farbe Schwarz gemischt.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch
- [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
