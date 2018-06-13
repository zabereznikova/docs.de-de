---
title: 'Gewusst wie: Konvertieren eines BMP-Bildes in ein PNG-Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: fd890c4f17b9759d37d7625526366034c664a71a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520785"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Gewusst wie: Konvertieren eines BMP-Bildes in ein PNG-Bild
Sie möchten sicher oft eine Datei von einem Bilddateiformat in ein anderes konvertieren. Sie können diese Konvertierung einfach durchführen, indem Sie die <xref:System.Drawing.Image.Save%2A>-Methode der <xref:System.Drawing.Image>-Klasse aufrufen und das <xref:System.Drawing.Imaging.ImageFormat> für das gewünschte Bilddateiformat angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein BMP-Bild eines Typs geladen und im PNG-Format gespeichert.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms-Anwendung  
  
-   Einen Verweis auf den `System.Drawing.Imaging`-Namespace  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Verwenden von Bildencodern und -decodern in Managed GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 [Typen von Bitmaps](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
