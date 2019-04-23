---
title: 'Vorgehensweise: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: c1051b234961eee9ae740af2abac3d64c523656c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227404"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="e1800-102">Vorgehensweise: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush</span><span class="sxs-lookup"><span data-stu-id="e1800-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="e1800-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.TileBrush> um ein Muster zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1800-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="e1800-104">Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft können Sie angeben, wie der Inhalt der ein <xref:System.Windows.Media.TileBrush> wird wiederholt, d. h., gekachelt, um einen Ausgabebereich auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="e1800-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="e1800-105">Um ein Muster zu erstellen, legen Sie die <xref:System.Windows.Media.TileBrush.TileMode%2A> zu <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, oder <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="e1800-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="e1800-106">Müssen Sie auch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> von der <xref:System.Windows.Media.TileBrush> , damit er kleiner als der Bereich ist, die Sie zeichnen werden; andernfalls nur eine einzige Kachel wird erstellt, unabhängig davon die <xref:System.Windows.Media.TileBrush.TileMode%2A> Einstellung, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1800-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1800-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1800-107">Example</span></span>  
 <span data-ttu-id="e1800-108">Das folgende Beispiel erstellt fünf <xref:System.Windows.Media.DrawingBrush> Objekte, erhalten sie jeden eine andere <xref:System.Windows.Media.TileBrush.TileMode%2A> festlegen und zum Zeichnen von fünf Rechtecken verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1800-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="e1800-109">Obwohl dieses Beispiel verwendet die <xref:System.Windows.Media.DrawingBrush> Klasse zur Veranschaulichung <xref:System.Windows.Media.TileBrush.TileMode%2A> Verhalten der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft funktioniert genauso wie für alle der <xref:System.Windows.Media.TileBrush> Objekte, d. h. für <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, und <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="e1800-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="e1800-110">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e1800-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="e1800-111">![TileBrush-Beispielausgabe tiling](./media/graphicsmm-drawingbrushtilemodeexample.png "Graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="e1800-111">![TileBrush tiling example output](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="e1800-112">Kachelmuster mit der TileMode-Eigenschaft erstellt</span><span class="sxs-lookup"><span data-stu-id="e1800-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e1800-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1800-113">See also</span></span>

- [<span data-ttu-id="e1800-114">Festlegen der Kachelgröße für ein TileBrush</span><span class="sxs-lookup"><span data-stu-id="e1800-114">Set the Tile Size for a TileBrush</span></span>](how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="e1800-115">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="e1800-115">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
