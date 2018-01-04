---
title: 'Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern'
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
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dde9417782e4404237a995364d65058f023c3e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern
Die <xref:System.Drawing.Bitmap> Klasse (geerbt von der <xref:System.Drawing.Image> Klasse) und die <xref:System.Drawing.Imaging.ImageAttributes> Klasse bieten Funktionen für Pixelwerte festlegen und abrufen. Können Sie die <xref:System.Drawing.Imaging.ImageAttributes> Klasse so ändern Sie den Alpha-Werte für ein vollständiges Bild, oder Sie rufen die <xref:System.Drawing.Bitmap.SetPixel%2A> Methode der <xref:System.Drawing.Bitmap> Klasse, um die einzelnen Pixels-Werte zu ändern.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Drawing.Imaging.ImageAttributes> -Klasse verfügt über zahlreiche Eigenschaften, die Sie verwenden können, während des Renderings Bilder ändern. Im folgenden Beispiel ein <xref:System.Drawing.Imaging.ImageAttributes> Objekt wird verwendet, um alle Alphawerte auf 80 Prozent des Originalwerts festgelegt. Dies erfolgt durch Initialisieren einer Farbmatrix und den Wert in der Matrix mit 0,8 Skalierung Alpha festlegen. An die Adresse der Farbmatrix übergeben wird die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> Methode der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt, und die <xref:System.Drawing.Imaging.ImageAttributes> -Objekt übergeben wird die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Objekt.  
  
 Beim Rendern, werden die Alphawerte in der Bitmap-80 % des Originalwerts konvertiert. Dies führt zu einem Bild, das mit dem Hintergrund gemischt ist. Wie in die folgende Abbildung gezeigt, sieht das Bitmap-Bild transparent; Sie können die durchgehende schwarze Linie durchzogen sehen.  
  
 ![Alphablending mit einer Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "Bild2")  
  
 Das Bild über den weißen Bereich des Hintergrunds vorhanden ist, hat das Bild mit der Farbe Weiß gemischt wurden. In dem das Bild für die schwarze Linie schneidet wird das Abbild mit der Farbe Schwarz gemischt.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
