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
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="30cdb-102">Vorgehensweise: Codieren eines Visual-Objekts in einer Bilddatei</span><span class="sxs-lookup"><span data-stu-id="30cdb-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="30cdb-103">In diesem Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Visual> <xref:System.Windows.Media.Imaging.RenderTargetBitmap> -Objekt mithilfe von und <xref:System.Windows.Media.Imaging.PngBitmapEncoder>in in eine Bilddatei codiert wird.</span><span class="sxs-lookup"><span data-stu-id="30cdb-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30cdb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30cdb-104">Example</span></span>  
 <span data-ttu-id="30cdb-105">Die <xref:System.Windows.Media.DrawingVisual> wird mit <xref:System.Windows.Media.Imaging.BitmapImage> <xref:System.Windows.Media.Imaging.RenderTargetBitmap>einem erstellt, das in einem gerendert wird. <xref:System.Windows.Media.FormattedText></span><span class="sxs-lookup"><span data-stu-id="30cdb-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="30cdb-106">Die gerenderte Bitmap wird dann verwendet, <xref:System.Windows.Media.Imaging.BitmapFrame> um einen zu erstellen, <xref:System.Windows.Media.Imaging.PngBitmapEncoder> der dem hinzugefügt wird, um eine neue Portable Network Graphics (PNG)-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="30cdb-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new Portable Network Graphics (PNG) file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="30cdb-107">In <xref:System.Windows.Media.Imaging.PngBitmapEncoder> diesem Beispiel wurde ein verwendet, aber eines der abgeleiteten <xref:System.Windows.Media.Imaging.BitmapEncoder> Objekte hätte zum Erstellen der Bilddatei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="30cdb-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30cdb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30cdb-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="30cdb-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="30cdb-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="30cdb-110">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="30cdb-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="30cdb-111">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="30cdb-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
