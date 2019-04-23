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
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189876"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="880c4-102">Vorgehensweise: Erstellen einer Bitmap aus einem visuellen Element</span><span class="sxs-lookup"><span data-stu-id="880c4-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="880c4-103">Dieses Beispiel zeigt, wie Sie eine Bitmap aus erstellen können eine <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="880c4-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="880c4-104">Ein <xref:System.Windows.Media.DrawingVisual> wird mit gerendert <xref:System.Windows.Media.FormattedText>.</span><span class="sxs-lookup"><span data-stu-id="880c4-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="880c4-105">Die <xref:System.Windows.Media.Visual> wird dann gerendert werden, um die <xref:System.Windows.Media.Imaging.RenderTargetBitmap> Erstellen eines Bitmaps des angegebenen Texts.</span><span class="sxs-lookup"><span data-stu-id="880c4-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="880c4-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="880c4-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="880c4-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="880c4-107">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="880c4-108">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="880c4-108">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="880c4-109">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="880c4-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="880c4-110">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="880c4-110">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
