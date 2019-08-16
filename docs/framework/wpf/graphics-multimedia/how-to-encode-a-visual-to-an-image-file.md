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
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545290"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Vorgehensweise: Codieren eines Visual-Objekts in einer Bilddatei
In diesem Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Visual> <xref:System.Windows.Media.Imaging.RenderTargetBitmap> -Objekt mithilfe von und <xref:System.Windows.Media.Imaging.PngBitmapEncoder>in in eine Bilddatei codiert wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.DrawingVisual> wird mit <xref:System.Windows.Media.Imaging.BitmapImage> <xref:System.Windows.Media.Imaging.RenderTargetBitmap>einem erstellt, das in einem gerendert wird. <xref:System.Windows.Media.FormattedText> Die gerenderte Bitmap wird dann verwendet, <xref:System.Windows.Media.Imaging.BitmapFrame> um einen zu erstellen, <xref:System.Windows.Media.Imaging.PngBitmapEncoder> der dem hinzugefügt wird, um eine neue Portable Network Graphics (PNG)-Datei zu erstellen.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 In <xref:System.Windows.Media.Imaging.PngBitmapEncoder> diesem Beispiel wurde ein verwendet, aber eines der abgeleiteten <xref:System.Windows.Media.Imaging.BitmapEncoder> Objekte hätte zum Erstellen der Bilddatei verwendet werden können.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingContext>
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md)
