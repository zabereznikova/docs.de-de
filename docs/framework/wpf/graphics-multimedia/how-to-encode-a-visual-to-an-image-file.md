---
title: 'Gewusst wie: Codieren eines Visual-Objekts in einer Bilddatei'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: a9e847a46941c37efb735d5bfd13bde2dd74271c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560162"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Gewusst wie: Codieren eines Visual-Objekts in einer Bilddatei
In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Visual> Objekt in ein Bild mit einem <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.DrawingVisual> erstellt, wobei eine <xref:System.Windows.Media.Imaging.BitmapImage> und <xref:System.Windows.Media.FormattedText> der wird gerendert, um eine <xref:System.Windows.Media.Imaging.RenderTargetBitmap>. Die gerenderte Bitmap wird dann zum Erstellen einer <xref:System.Windows.Media.Imaging.BitmapFrame> die hinzugefügt wird die <xref:System.Windows.Media.Imaging.PngBitmapEncoder> zum Erstellen eines neuen [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] Datei.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder> wurde in diesem Beispiel jedoch eine der abgeleiteten verwendet <xref:System.Windows.Media.Imaging.BitmapEncoder> Objekte wurden zum Erzeugen der Abbilddatei verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingContext>  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
