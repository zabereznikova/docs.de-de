---
title: Zeichnen, Positionieren und Klonen von Bildern in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: 5ff502884874e21e8f34acb2f15db4c651a0a273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521650"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>Zeichnen, Positionieren und Klonen von Bildern in GDI+
Können Sie die <xref:System.Drawing.Bitmap> Klasse zum Laden und Anzeigen von Rasterbildern, und Sie können die <xref:System.Drawing.Imaging.Metafile> Klasse zum Laden und Anzeigen von Vektorgrafiken. Die <xref:System.Drawing.Bitmap> und <xref:System.Drawing.Imaging.Metafile> Klassen erben von der <xref:System.Drawing.Image> Klasse. Um ein Image des Vektors anzuzeigen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Imaging.Metafile>. Um ein Rasterbild anzuzeigen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Bitmap>. Die Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode, die empfängt die <xref:System.Drawing.Imaging.Metafile> oder <xref:System.Drawing.Bitmap> als Argument.  
  
## <a name="file-types-and-cloning"></a>Dateitypen und Klonen  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Drawing.Bitmap> aus der Datei Climber.jpg und zeigt die Bitmap. Der Zielort für die linke obere Ecke des Bilds, (10, 10), in der zweiten und dritten Parameter angegeben ist.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 Die folgende Abbildung zeigt das Bild an.  
  
 ![Abbildung Beispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 Das Konstruieren von <xref:System.Drawing.Bitmap> Objekte aus einer Vielzahl von Grafiken Dateiformate: BMP, GIF, JPEG, EXIF, PNG, TIFF und Symbol.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Konstruieren <xref:System.Drawing.Bitmap> Objekte aus einer Vielzahl von Dateitypen und zeigt dann die Bitmaps.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 Die <xref:System.Drawing.Bitmap> Klasse bietet einen <xref:System.Drawing.Bitmap.Clone%2A> -Methode, die Sie verwenden können, um eine Kopie eines vorhandenen <xref:System.Drawing.Bitmap>. Die <xref:System.Drawing.Bitmap.Clone%2A> -Methode besitzt einen Quelle Rechteck-Parameter, die Sie verwenden können, um den Teil der ursprünglichen Bitmap anzugeben, die Sie kopieren möchten. Das folgende Codebeispiel veranschaulicht das Erstellen einer <xref:System.Drawing.Bitmap> durch Klonen die obere Hälfte eines vorhandenen <xref:System.Drawing.Bitmap>. Dann werden beide Bilder gezeichnet.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 Die folgende Abbildung zeigt die beiden Images.  
  
 ![Zuschneiden](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
