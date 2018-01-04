---
title: 'Gewusst wie: Zeichnen eines Bilds mit ImageDrawing'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d292617ef18bea32396327fd1b0a1d08d35ee16f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="a2f1c-102">Gewusst wie: Zeichnen eines Bilds mit ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="a2f1c-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="a2f1c-103">Dieses Beispiel zeigt, wie ein <xref:System.Windows.Media.ImageDrawing> ein Bild gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2f1c-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="a2f1c-104">Ein <xref:System.Windows.Media.ImageDrawing> ermöglicht, die Sie anzeigen, eine <xref:System.Windows.Media.ImageSource> mit einem <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, oder <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="a2f1c-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="a2f1c-105">Um ein Bild gezeichnet werden soll, erstellen Sie eine <xref:System.Windows.Media.ImageDrawing> und legen Sie dessen <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a2f1c-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="a2f1c-106">Die <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> -Eigenschaft gibt das Bild gezeichnet werden soll, und die <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> Eigenschaft gibt die Position und Größe jedes Bilds.</span><span class="sxs-lookup"><span data-stu-id="a2f1c-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2f1c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2f1c-107">Example</span></span>  
 <span data-ttu-id="a2f1c-108">Das folgende Beispiel erstellt eine zusammengesetzte Zeichnung mit vier <xref:System.Windows.Media.ImageDrawing> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a2f1c-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="a2f1c-109">Dieses Beispiel erzeugt die folgende Abbildung:</span><span class="sxs-lookup"><span data-stu-id="a2f1c-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="a2f1c-110">![Mehrere DrawingImage-Objekte](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "Graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="a2f1c-110">![Several DrawingImage objects](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="a2f1c-111">Vier ImageDrawing-Objekte</span><span class="sxs-lookup"><span data-stu-id="a2f1c-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="a2f1c-112">Ein Beispiel für eine einfache Möglichkeit zum Anzeigen eines Bilds ohne <xref:System.Windows.Media.ImageDrawing>, finden Sie unter [verwenden das Bildelement](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="a2f1c-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f1c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2f1c-113">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [<span data-ttu-id="a2f1c-114">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="a2f1c-114">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="a2f1c-115">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="a2f1c-115">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="a2f1c-116">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="a2f1c-116">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
