---
title: 'Gewusst wie: Erstellen einer Bitmap mit einem visuellen Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db3ad547072f1d9162ede5c45144aa30e809c50e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Gewusst wie: Erstellen einer Bitmap mit einem visuellen Element
Dieses Beispiel zeigt die Erstellung einer Bitmap aus einem <xref:System.Windows.Media.Visual>. Ein <xref:System.Windows.Media.DrawingVisual> wird beim Rendering <xref:System.Windows.Media.FormattedText>. Die <xref:System.Windows.Media.Visual> wird dann gerendert werden, auf die <xref:System.Windows.Media.Imaging.RenderTargetBitmap> Erstellen eines Bitmaps des angegebenen Texts.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingContext>  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
