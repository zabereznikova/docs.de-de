---
title: 'Vorgehensweise: Erstellen einer Bitmap aus einem visuellen Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 429aacc99d8ead5a18e9be7602b19a74773b419a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362863"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Vorgehensweise: Erstellen einer Bitmap aus einem visuellen Element
Dieses Beispiel zeigt, wie Sie eine Bitmap aus erstellen können eine <xref:System.Windows.Media.Visual>. Ein <xref:System.Windows.Media.DrawingVisual> wird mit gerendert <xref:System.Windows.Media.FormattedText>. Die <xref:System.Windows.Media.Visual> wird dann gerendert werden, um die <xref:System.Windows.Media.Imaging.RenderTargetBitmap> Erstellen eines Bitmaps des angegebenen Texts.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.DrawingContext>
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md)
