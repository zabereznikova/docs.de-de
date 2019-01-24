---
title: 'Vorgehensweise: Codieren eines Visual-Objekts in einer Bilddatei'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: e8988256d4b7181c5e1af12252ca26e0248d016f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645222"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Vorgehensweise: Codieren eines Visual-Objekts in einer Bilddatei
In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Visual> Objekt in ein Bild mit einer <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.DrawingVisual> wurde mit einem <xref:System.Windows.Media.Imaging.BitmapImage> und <xref:System.Windows.Media.FormattedText> die gerendert wird, um eine <xref:System.Windows.Media.Imaging.RenderTargetBitmap>. Die gerenderte Bitmap wird dann zum Erstellen einer <xref:System.Windows.Media.Imaging.BitmapFrame> hinzugefügt wird und auf die <xref:System.Windows.Media.Imaging.PngBitmapEncoder> zum Erstellen eines neuen [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] Datei.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder> verwendet wurde, in diesem Beispiel jedoch eine der abgeleiteten <xref:System.Windows.Media.Imaging.BitmapEncoder> Objekte hätten verwendet werden können, erstellen Sie die Image-Datei.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.DrawingContext>
- [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
- [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
