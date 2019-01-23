---
title: Zuschneiden und Skalieren von Bildern in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: 6c3ad0892ea0892b7c4c0e21e14bdb75fe22b447
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554217"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Zuschneiden und Skalieren von Bildern in GDI+
Können Sie die <xref:System.Drawing.Graphics.DrawImage%2A> Methode der <xref:System.Drawing.Graphics> Klasse zeichnen und Positionieren von Vektor- und Rasterbildern. <xref:System.Drawing.Graphics.DrawImage%2A> eine überladene Methode, ist, damit es gibt mehrere Möglichkeiten, die Sie diese mit Argumenten bereitstellen können.  
  
## <a name="drawimage-variations"></a>DrawImage-Varianten  
 Eine Variante der der <xref:System.Drawing.Graphics.DrawImage%2A> -Methode empfängt einen <xref:System.Drawing.Bitmap> und <xref:System.Drawing.Rectangle>. Das Rechteck gibt an, das Ziel für den Zeichenvorgang; Das heißt, gibt es das Rechteck, in dem das Bild gezeichnet werden soll. Wenn die Größe des Zielrechtecks von der Größe des ursprünglichen Bilds ist, wird das Bild skaliert um Zielrechtecks zu passen. Im folgenden Codebeispiel wird veranschaulicht, wie das gleiche Bild dreimal gezeichnet: einmal ohne Skalierung, einmal mit der eine Erweiterung und einmal mit einer Komprimierung:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 Die folgende Abbildung zeigt die drei Bilder.  
  
 ![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Einige Varianten der <xref:System.Drawing.Graphics.DrawImage%2A> Methode haben, einem Quellrechteck als auch in ein Zielrechteck-Parameter. Der Quellrechteck Parameter gibt an, der Teil des ursprünglichen Bilds gezeichnet wird. Das Zielrechteck gibt das Rechteck, in dem dieser Teil des Bilds gezeichnet werden soll. Wenn die Größe des Zielrechtecks von der Größe des Quellrechtecks ist, wird das Bild skaliert um Zielrechtecks zu passen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Drawing.Bitmap> aus der Datei Runner.jpg. Das gesamte Bild ohne Skalierung auf gezeichnet wird (0, 0). Und klicken Sie dann zweimal ein kleiner Teil des Bilds gezeichnet ist: einmal mit Komprimierung und einmal mit einer Erweiterung.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 Die folgende Abbildung zeigt das Bild, und die komprimierte und erweiterte Bild Teile.  
  
 ![Zuschneiden und Skalieren von](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Siehe auch
- [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
