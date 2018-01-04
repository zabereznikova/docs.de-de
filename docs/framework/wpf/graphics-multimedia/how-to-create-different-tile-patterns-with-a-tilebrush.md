---
title: 'Gewusst wie: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush'
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
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646ce5142875c95c0b1ca19643790f73f7eb83e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="da677-102">Gewusst wie: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush</span><span class="sxs-lookup"><span data-stu-id="da677-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="da677-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.TileBrush> um ein Muster zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da677-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="da677-104">Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft können Sie angeben, wie die Inhalts des eine <xref:System.Windows.Media.TileBrush> wird wiederholt, d. h., gekachelt, um einen Ausgabebereich ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="da677-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="da677-105">Um ein Muster zu erstellen, Sie legen die <xref:System.Windows.Media.TileBrush.TileMode%2A> auf <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, oder <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="da677-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="da677-106">Müssen Sie auch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> von der <xref:System.Windows.Media.TileBrush> , damit es kleiner ist als der Bereich handelt, die zu zeichnenden; hingegen nur eine einzige Kachel wird erzeugt, unabhängig davon die <xref:System.Windows.Media.TileBrush.TileMode%2A> Einstellung, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="da677-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da677-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da677-107">Example</span></span>  
 <span data-ttu-id="da677-108">Das folgende Beispiel erstellt fünf <xref:System.Windows.Media.DrawingBrush> Objekte, erhalten sie jede ein anderes <xref:System.Windows.Media.TileBrush.TileMode%2A> festlegen und verwendet sie zum Zeichnen von fünf Rechtecken.</span><span class="sxs-lookup"><span data-stu-id="da677-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="da677-109">Obwohl in diesem Beispiel verwendet die <xref:System.Windows.Media.DrawingBrush> Klasse zur Veranschaulichung der Funktion <xref:System.Windows.Media.TileBrush.TileMode%2A> Verhalten, die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft funktioniert genauso wie für alle der <xref:System.Windows.Media.TileBrush> Objekte aufweist, d. h. für <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, und <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="da677-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="da677-110">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="da677-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="da677-111">![TileBrush Kacheln Beispielausgabe](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "Graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="da677-111">![TileBrush tiling example output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="da677-112">Kachel-Muster, die mit der TileMode-Eigenschaft erstellt</span><span class="sxs-lookup"><span data-stu-id="da677-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="da677-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da677-113">See Also</span></span>  
 [<span data-ttu-id="da677-114">Festlegen der Kachelgröße für ein TileBrush</span><span class="sxs-lookup"><span data-stu-id="da677-114">Set the Tile Size for a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [<span data-ttu-id="da677-115">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="da677-115">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
