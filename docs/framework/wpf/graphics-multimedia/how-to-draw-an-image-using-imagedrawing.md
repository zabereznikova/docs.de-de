---
title: 'Vorgehensweise: Zeichnen eines Bilds mit einer ImageDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100157"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="3fb56-102">Vorgehensweise: Zeichnen eines Bilds mit einer ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="3fb56-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="3fb56-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.ImageDrawing> Zeichnen eines Bildes.</span><span class="sxs-lookup"><span data-stu-id="3fb56-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="3fb56-104">Ein <xref:System.Windows.Media.ImageDrawing> ermöglicht, die Sie anzeigen, eine <xref:System.Windows.Media.ImageSource> mit einem <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, oder <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="3fb56-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="3fb56-105">Um ein Bild zu zeichnen, erstellen Sie eine <xref:System.Windows.Media.ImageDrawing> und legen Sie dessen <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3fb56-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="3fb56-106">Die <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> Eigenschaft gibt an, das Bild zu zeichnen, und die <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> Eigenschaft gibt an, die Position und Größe der einzelnen Bilder.</span><span class="sxs-lookup"><span data-stu-id="3fb56-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb56-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fb56-107">Example</span></span>  
 <span data-ttu-id="3fb56-108">Das folgende Beispiel erstellt eine zusammengesetzte Zeichnung mit vier <xref:System.Windows.Media.ImageDrawing> Objekte.</span><span class="sxs-lookup"><span data-stu-id="3fb56-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="3fb56-109">Dieses Beispiel erzeugt die folgende Abbildung:</span><span class="sxs-lookup"><span data-stu-id="3fb56-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="3fb56-110">![Mehrere DrawingImage-Objekte](./media/graphicsmm-imagedrawingexample.jpg "Graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="3fb56-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="3fb56-111">Vier ImageDrawing-Objekte</span><span class="sxs-lookup"><span data-stu-id="3fb56-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="3fb56-112">Ein Beispiel für eine einfache Möglichkeit zum Anzeigen eines Bilds ohne <xref:System.Windows.Media.ImageDrawing>, finden Sie unter [verwenden Sie das Image-Element](../controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="3fb56-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb56-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fb56-113">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="3fb56-114">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="3fb56-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="3fb56-115">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="3fb56-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="3fb56-116">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="3fb56-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
